---
title: 'SQL : Relationship et la règle de classement des clés (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sql:relationship
- key ordering rules [SQLXML]
- relationship annotation
ms.assetid: 914cb152-09f5-4b08-b35d-71940e4e9986
author: rothja
ms.author: jroth
ms.openlocfilehash: 716e911676dc81539fc641bee139d92e29dc49db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611710"
---
# <a name="sqlrelationship-and-the-key-ordering-rule-sqlxml-40"></a><span data-ttu-id="1cc89-102">sql:relationship et la règle de tri par clé (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="1cc89-102">sql:relationship and the Key Ordering Rule (SQLXML 4.0)</span></span>
  <span data-ttu-id="1cc89-103">Dans la mesure où la fonctionnalité de chargement en masse XML génère des enregistrements lorsque les nœuds de ces derniers entrent dans l'étendue, et qu'elle envoie ces enregistrements à Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] lorsque les nœuds correspondants sortent de l'étendue, les données de l'enregistrement doivent être présentes dans l'étendue du nœud.</span><span class="sxs-lookup"><span data-stu-id="1cc89-103">Because XML Bulk Load generates records as their nodes enter into scope and sends those records to Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as their nodes exit scope, the data for the record must be present within the scope of the node.</span></span>  
  
 <span data-ttu-id="1cc89-104">Prenons le schéma XSD suivant, dans lequel la relation un-à-plusieurs entre **\<Customer>** les **\<Order>** éléments et (un client peut passer plusieurs commandes) est spécifiée à l’aide de l' `<sql:relationship>` élément :</span><span class="sxs-lookup"><span data-stu-id="1cc89-104">Consider the following XSD schema, in which the one-to-many relationship between **\<Customer>** and **\<Order>** elements (one customer can place many orders) is specified by using the `<sql:relationship>` element:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"<>   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustCustOrder"  
          parent="Cust"  
          parent-key="CustomerID"  
          child="CustOrder"  
          child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customers" sql:relation="Cust" >  
   <xsd:complexType>  
     <xsd:sequence>  
       <xsd:element name="CustomerID"  type="xsd:integer" />  
       <xsd:element name="CompanyName" type="xsd:string" />  
       <xsd:element name="City"        type="xsd:string" />  
       <xsd:element name="Order"   
                          sql:relation="CustOrder"  
                          sql:relationship="CustCustOrder" >  
         <xsd:complexType>  
          <xsd:attribute name="OrderID" type="xsd:integer" />  
         </xsd:complexType>  
       </xsd:element>  
     </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="1cc89-105">Lorsque le **\<Customer>** nœud d’élément entre dans l’étendue, le chargement en masse XML génère un enregistrement de client.</span><span class="sxs-lookup"><span data-stu-id="1cc89-105">As the **\<Customer>** element node enters into scope, XML Bulk Load generates a customer record.</span></span> <span data-ttu-id="1cc89-106">Cet enregistrement est conservé jusqu’à la lecture du chargement en masse XML **\</Customer>** .</span><span class="sxs-lookup"><span data-stu-id="1cc89-106">This record stays until XML Bulk Load reads **\</Customer>**.</span></span> <span data-ttu-id="1cc89-107">Lors du traitement du **\<Order>** nœud d’élément, le chargement en masse XML utilise `<sql:relationship>` pour obtenir la valeur de la colonne de clé étrangère CustomerID de la table CustOrder à partir de l' **\<Customer>** élément parent, car l' **\<Order>** élément ne spécifie pas l’attribut **CustomerID** .</span><span class="sxs-lookup"><span data-stu-id="1cc89-107">In processing the **\<Order>** element node, XML Bulk Load uses `<sql:relationship>` to obtain the value of the CustomerID foreign key column of the CustOrder table from the **\<Customer>** parent element, because the **\<Order>** element does not specify the **CustomerID** attribute.</span></span> <span data-ttu-id="1cc89-108">Cela signifie que lors de la définition de l' **\<Customer>** élément, vous devez spécifier l’attribut **CustomerID** dans le schéma avant de spécifier `<sql:relationship>` .</span><span class="sxs-lookup"><span data-stu-id="1cc89-108">This means that in defining the **\<Customer>** element, you must specify the **CustomerID** attribute in the schema before you specify `<sql:relationship>`.</span></span> <span data-ttu-id="1cc89-109">Dans le cas contraire, lorsqu’un **\<Order>** élément entre dans l’étendue, le chargement en masse XML génère un enregistrement pour la table CustOrder et, lorsque le chargement en masse XML atteint la **\</Order>** balise de fin, il envoie l’enregistrement à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sans la valeur de la colonne de clé étrangère CustomerID.</span><span class="sxs-lookup"><span data-stu-id="1cc89-109">Otherwise, when an **\<Order>** element enters into scope, XML Bulk Load generates a record for the CustOrder table, and when the XML Bulk Load reaches the **\</Order>** end tag, it sends the record to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] without the CustomerID foreign key column value.</span></span>  
  
 <span data-ttu-id="1cc89-110">Enregistrez le schéma fourni dans cet exemple sous le nom SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="1cc89-110">Save the schema that is provided in this example as SampleSchema.xml.</span></span>  
  
### <a name="to-test-a-working-sample"></a><span data-ttu-id="1cc89-111">Pour tester un exemple fonctionnel</span><span class="sxs-lookup"><span data-stu-id="1cc89-111">To test a working sample</span></span>  
  
1.  <span data-ttu-id="1cc89-112">Créez les tables suivantes :</span><span class="sxs-lookup"><span data-stu-id="1cc89-112">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Cust (  
                  CustomerID     int          PRIMARY KEY,  
               CompanyName    varchar(20)  NOT NULL,  
                  City           varchar(20)  DEFAULT 'Seattle')  
    GO  
    CREATE TABLE CustOrder (  
                  OrderID        varchar(10) PRIMARY KEY,  
               CustomerID     int         FOREIGN KEY REFERENCES                                          Cust(CustomerID))  
    GO  
    ```  
  
2.  <span data-ttu-id="1cc89-113">Enregistrez l'exemple de données ci-après sous le nom SampleXMLData.xml :</span><span class="sxs-lookup"><span data-stu-id="1cc89-113">Save the following sample data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>    
      <Customers>  
        <CompanyName>Hanari Carnes</CompanyName>  
        <City>NY</City>  
        <Order OrderID="1" />  
        <Order OrderID="2" />  
        <CustomerID>1111</CustomerID>  
      </Customers>  
      <Customers>  
        <CompanyName>Toms Spezialitten</CompanyName>  
         <City>LA</City>    
        <Order OrderID="3" />  
        <CustomerID>1112</CustomerID>  
      </Customers>  
      <Customers>  
        <CompanyName>Victuailles en stock</CompanyName>  
        <Order OrderID="4" />  
        <CustomerID>1113</CustomerID>  
      </Customers>  
    </ROOT>  
    ```  
  
3.  <span data-ttu-id="1cc89-114">Pour effectuer le chargement en masse XML, enregistrez l'exemple [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) suivant sous le nom MySample.vbs, puis exécutez-le :</span><span class="sxs-lookup"><span data-stu-id="1cc89-114">To execute XML Bulk Load, save and execute the following [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) example as MySample.vbs:</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Transaction=True  
    objBL.Execute "c:\SampleSchema.xml", "c:\SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
     <span data-ttu-id="1cc89-115">Il en résulte que la fonctionnalité de chargement en masse XML insère une valeur NULL dans la colonne de clé étrangère CustomerID de la table CustOrder.</span><span class="sxs-lookup"><span data-stu-id="1cc89-115">The result is that XML Bulk Load inserts a NULL value in the CustomerID foreign key column of the CustOrder table.</span></span> <span data-ttu-id="1cc89-116">Si vous modifiez l’exemple de données XML de sorte que l' **\<CustomerID>** élément enfant apparaisse avant l' **\<Order>** élément enfant, vous obtenez le résultat attendu : le chargement en masse XML insère la valeur de clé étrangère spécifiée dans la colonne.</span><span class="sxs-lookup"><span data-stu-id="1cc89-116">If you revise the XML sample data so that the **\<CustomerID>** child element appears before the **\<Order>** child element, you get the expected result: XML Bulk Load inserts the specified foreign key value into the column.</span></span>  
  
 <span data-ttu-id="1cc89-117">Voici le schéma XDR équivalent :</span><span class="sxs-lookup"><span data-stu-id="1cc89-117">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >   
   <ElementType name="CustomerID"  />  
   <ElementType name="CompanyName" />  
   <ElementType name="City"        />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust" >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
                 <sql:relationship  
                        key-relation    ="Cust"  
                        key             ="CustomerID"  
                        foreign-key     ="CustomerID"  
                        foreign-relation="CustOrder" />  
      </element>  
   </ElementType>  
    <ElementType name="Order" sql:relation="CustOrder" >  
      <AttributeType name="OrderID" />  
      <AttributeType name="CustomerID" />  
      <attribute type="OrderID" />  
      <attribute type="CustomerID" />  
    </ElementType>  
</Schema>  
```  
  
  
