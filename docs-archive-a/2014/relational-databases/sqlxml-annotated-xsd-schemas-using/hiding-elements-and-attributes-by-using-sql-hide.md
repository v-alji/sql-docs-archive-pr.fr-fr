---
title: 'Masquage d’éléments et d’attributs à l’aide de SQL : Hide | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- hiding elements
- element mapping [SQLXML], hiding attributes and elements
- hide annotation
- sql:hide
- table/view mapping [SQLXML], hiding attributes and elements
- table mapping [SQLXML], hiding attributes and elements
- hiding attributes
- annotated XSD schemas, hiding attributes and elements
- attribute mapping [SQLXML], hiding attributes and elements
- column mapping [SQLXML]
- element hiding [SQLXML]
- XSD schemas [SQLXML], hiding attributes and elements
- attribute hiding [SQLXML]
ms.assetid: 0978301b-f068-46b6-82b9-dc555161f52e
author: rothja
ms.author: jroth
ms.openlocfilehash: 5a3beb48be1d9809b170faeafa964ba45156ac28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709031"
---
# <a name="hiding-elements-and-attributes-by-using-sqlhide"></a><span data-ttu-id="a19ff-102">Masquage d'éléments et d'attributs à l'aide de sql:hide</span><span class="sxs-lookup"><span data-stu-id="a19ff-102">Hiding Elements and Attributes by Using sql:hide</span></span>
  <span data-ttu-id="a19ff-103">Lorsqu'une requête XPath est exécutée contre un schéma XSD, le document XML résultant possède des éléments et des attributs spécifiés dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="a19ff-103">When an XPath query is executed against an XSD schema, the resulting XML document has elements and attributes that are specified in the schema.</span></span> <span data-ttu-id="a19ff-104">Vous pouvez spécifier que certains éléments et attributs soient masqués dans le schéma en utilisant l'annotation `sql:hide`.</span><span class="sxs-lookup"><span data-stu-id="a19ff-104">You can specify that some elements and attributes be hidden in the schema by using the `sql:hide` annotation.</span></span> <span data-ttu-id="a19ff-105">Cela est utile lorsque les critères de sélection de la requête requièrent des éléments ou des attributs particuliers dans le schéma, mais que vous ne souhaitez pas les retourner dans le document XML généré.</span><span class="sxs-lookup"><span data-stu-id="a19ff-105">This is useful when the selection criteria of the query require particular elements or attributes in the schema, but you do not want them returned in the XML document that is generated.</span></span>  
  
 <span data-ttu-id="a19ff-106">L'annotation `sql:hide` prend une valeur booléenne (0=faux, 1=vrai).</span><span class="sxs-lookup"><span data-stu-id="a19ff-106">The `sql:hide` annotation takes a Boolean value (0=false, 1=true).</span></span> <span data-ttu-id="a19ff-107">Les valeurs acceptables sont 0, 1, true et false.</span><span class="sxs-lookup"><span data-stu-id="a19ff-107">The acceptable values are 0, 1, true, and false.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a19ff-108">Exemples</span><span class="sxs-lookup"><span data-stu-id="a19ff-108">Examples</span></span>  
 <span data-ttu-id="a19ff-109">Pour créer des exemples fonctionnels à l'aide des exemples suivants, vous devez répondre à certaines conditions requises.</span><span class="sxs-lookup"><span data-stu-id="a19ff-109">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="a19ff-110">Pour plus d’informations, consultez [Configuration requise pour l’exécution d’exemples SQLXML](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="a19ff-110">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqlhide-on-an-attribute"></a><span data-ttu-id="a19ff-111">R.</span><span class="sxs-lookup"><span data-stu-id="a19ff-111">A.</span></span> <span data-ttu-id="a19ff-112">Spécification de sql:hide sur un attribut</span><span class="sxs-lookup"><span data-stu-id="a19ff-112">Specifying sql:hide on an attribute</span></span>  
 <span data-ttu-id="a19ff-113">Le schéma XSD de cet exemple se compose d’un **\<Person.Contact>** élément avec les attributs **ContactID**, **FirstName**et **LastName** .</span><span class="sxs-lookup"><span data-stu-id="a19ff-113">The XSD schema in this example consists of an **\<Person.Contact>** element with **ContactID**, **FirstName**, and **LastName** attributes.</span></span>  
  
 <span data-ttu-id="a19ff-114">L' **\<Person.Contact>** élément est de type complexe et, par conséquent, est mappé à la table du même nom (mappage par défaut).</span><span class="sxs-lookup"><span data-stu-id="a19ff-114">The **\<Person.Contact>** element is of complex type and, therefore, maps to the table of the same name (default mapping).</span></span> <span data-ttu-id="a19ff-115">Tous les attributs de l' **\<Person.Contact>** élément sont de type simple et sont mappés à des colonnes portant le même nom dans Person. Contacttable dans la base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="a19ff-115">All the attributes of **\<Person.Contact>** element are of simple type and map to columns with the same names in the Person.Contacttable in the AdventureWorks database.</span></span> <span data-ttu-id="a19ff-116">Dans le schéma, l' `sql:hide` annotation est spécifiée sur l’attribut **ContactID** .</span><span class="sxs-lookup"><span data-stu-id="a19ff-116">In the schema, the `sql:hide` annotation is specified on the **ContactID** attribute.</span></span> <span data-ttu-id="a19ff-117">Lorsqu’une requête XPath est spécifiée sur ce schéma, le **ContactID** n’est pas renvoyé dans le document XML.</span><span class="sxs-lookup"><span data-stu-id="a19ff-117">When an XPath query is specified against this schema, the **ContactID** is not returned in the XML document.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact" >  
     <xsd:complexType>  
       <xsd:attribute name="ContactID"  sql:hide="true" />   
       <xsd:attribute name="FirstName"   type="xsd:string" />   
       <xsd:attribute name="LastName"    type="xsd:string" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="a19ff-118">Pour tester un exemple de requête XPath sur le schéma</span><span class="sxs-lookup"><span data-stu-id="a19ff-118">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="a19ff-119">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="a19ff-119">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="a19ff-120">Enregistrez le fichier sous le nom Hide.xml.</span><span class="sxs-lookup"><span data-stu-id="a19ff-120">Save the file as Hide.xml.</span></span>  
  
2.  <span data-ttu-id="a19ff-121">Copiez le modèle suivant et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="a19ff-121">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="a19ff-122">Enregistrez le fichier sous le nom HideT.xml dans le répertoire où vous avez enregistré le fichier Hide.xml.</span><span class="sxs-lookup"><span data-stu-id="a19ff-122">Save the file as HideT.xml in the same directory where you saved Hide.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="Hide.xml">  
            /Person.Contact[@ContactID="1"]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="a19ff-123">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (Hide.xml) est relatif au répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="a19ff-123">The directory path specified for the mapping schema (Hide.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="a19ff-124">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="a19ff-124">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\Hide.xml"  
    ```  
  
3.  <span data-ttu-id="a19ff-125">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="a19ff-125">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="a19ff-126">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="a19ff-126">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="a19ff-127">Voici l'ensemble de résultats obtenu :</span><span class="sxs-lookup"><span data-stu-id="a19ff-127">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
   <Person.Contact FirstName="Gustavo" LastName="Achong" />   
</ROOT>  
```  
  
 <span data-ttu-id="a19ff-128">Lorsque `sql:hide` est spécifié sur un élément, celui-ci et ses attributs ou éléments enfants n'apparaissent pas dans le document XML généré.</span><span class="sxs-lookup"><span data-stu-id="a19ff-128">When `sql:hide` is specified on an element, the element and its attributes or child elements do not appear in the XML document that is generated.</span></span> <span data-ttu-id="a19ff-129">Voici un autre schéma XSD dans lequel `sql:hide` est spécifié sur l' **\<OD>** élément :</span><span class="sxs-lookup"><span data-stu-id="a19ff-129">Here is another XSD schema in which `sql:hide` is specified on the **\<OD>** element:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:annotation>  
    <xsd:documentation>  
      Sales.Customer-Sales.SalesOrderHeader-Sales.SalesOrderDetail Schema  
      Copyright 2004 Microsoft. All rights reserved.  
    </xsd:documentation>  
    <xsd:appinfo>  
      <sql:relationship name="CustomerOrder"  
         parent="Sales.Customer"  
                  parent-key="CustomerID"  
                  child-key="CustomerID"  
                  child="Sales.SalesOrderHeader" />  
       <sql:relationship name="OrderOrderDetails"  
                  parent="Sales.SalesOrderHeader"  
                  parent-key="SalesOrderID"  
                  child-key="SalesOrderID"  
                  child="Sales.SalesOrderDetail"/>  
    </xsd:appinfo>  
  </xsd:annotation>  
  
  <xsd:element name="Customers" sql:relation="Sales.Customer">  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"   
                     maxOccurs="unbounded"   
                     sql:relationship="CustomerOrder">  
          <xsd:complexType>  
            <xsd:sequence>  
               <xsd:element name="OD" sql:relation="Sales.SalesOrderDetail"                                       maxOccurs="unbounded"                                       sql:relationship="OrderOrderDetails"                                       sql:hide="1">  
                  <xsd:complexType>  
                    <xsd:attribute name="SalesOrderID" type="xsd:string"/>  
                    <xsd:attribute name="ProductID" type="xsd:string"/>  
                  </xsd:complexType>  
               </xsd:element>  
            </xsd:sequence>  
          <xsd:attribute name="CustomerID" type="xsd:string"/>  
          <xsd:attribute name="OID" sql:field="SalesOrderID"   
                                    type="xsd:string"/>  
          <xsd:attribute name="OrderDate" type="xsd:date"/>   
        </xsd:complexType>  
      </xsd:element>  
    </xsd:sequence>  
    <xsd:attribute name="CID" sql:field="CustomerID"   
                                type="xsd:string"/>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="a19ff-130">Lorsqu’une requête XPath (par exemple `/Customers[@CID="1"]` ) est spécifiée par rapport à ce schéma, le document XML généré n’inclut pas l' **\<OD>** élément et ses enfants, comme indiqué dans ce résultat partiel :</span><span class="sxs-lookup"><span data-stu-id="a19ff-130">When an XPath query (for example `/Customers[@CID="1"]`) is specified against this schema, the XML document that is generated does not include the **\<OD>** element and its children, as shown in this partial result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customers CID="1">  
    <Order CustomerID="1" OID="43860" OrderDate="2001-08-01" />   
    <Order CustomerID="1" OID="44501" OrderDate="2001-11-01" />   
    <Order CustomerID="1" OID="45283" OrderDate="2002-02-01" />   
    <Order CustomerID="1" OID="46042" OrderDate="2002-05-01" />   
  </Customers>  
</ROOT>  
```  
  
  
