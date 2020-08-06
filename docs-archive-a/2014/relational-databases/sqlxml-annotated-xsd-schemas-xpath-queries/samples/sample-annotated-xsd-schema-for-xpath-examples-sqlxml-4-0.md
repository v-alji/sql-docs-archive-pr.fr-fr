---
title: Exemple de schéma XSD annoté pour les exemples XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], annotated XSD schemas in queries
- annotated XSD schemas, samples
- annotated XSD schemas, queries
ms.assetid: fefa2cc8-2d3c-4336-aeae-ce063a3a8df2
author: rothja
ms.author: jroth
ms.openlocfilehash: 7c7065bed89d867dda3ecffc7d80f2f729832e2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600743"
---
# <a name="sample-annotated-xsd-schema-for-xpath-examples-sqlxml-40"></a><span data-ttu-id="0e226-102">Exemple de schéma XSD annoté pour les exemples XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="0e226-102">Sample Annotated XSD Schema for XPath Examples (SQLXML 4.0)</span></span>
  <span data-ttu-id="0e226-103">Les exemples de requêtes XPath de cette section font référence à un schéma de mappage.</span><span class="sxs-lookup"><span data-stu-id="0e226-103">The sample XPath queries in this section refer to a mapping schema.</span></span> <span data-ttu-id="0e226-104">Le schéma de mappage est un fichier de schéma XML (XSD) annoté.</span><span class="sxs-lookup"><span data-stu-id="0e226-104">The mapping schema is an annotated XML Schema (XSD) file.</span></span> <span data-ttu-id="0e226-105">Pour plus d’informations sur le mappage des schémas, consultez [Introduction aux schémas XSD Annotés &#40;SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="0e226-105">For more information about mapping schemas, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="0e226-106">Les éléments suivants sont nécessaires pour exécuter des requêtes XPath sur un schéma XSD annoté :</span><span class="sxs-lookup"><span data-stu-id="0e226-106">The following are needed to execute XPath queries against an annotated XSD schema:</span></span>  
  
-   <span data-ttu-id="0e226-107">Créez un modèle contenant une requête XPath.</span><span class="sxs-lookup"><span data-stu-id="0e226-107">Create a template with an XPath query in it.</span></span> <span data-ttu-id="0e226-108">Dans le modèle, vous spécifiez le schéma de mappage sur lequel la requête XPath doit être exécutée.</span><span class="sxs-lookup"><span data-stu-id="0e226-108">In the template, you specify the mapping schema against which the XPath query is to be executed.</span></span> <span data-ttu-id="0e226-109">Dans ce cas, le schéma de mappage doit être stocké dans le répertoire (ou l'un de ses sous-répertoires, auquel cas un chemin d'accès relatif est spécifié comme valeur de l'attribut `mapping-schema` dans le modèle) associé au fichier de modèle.</span><span class="sxs-lookup"><span data-stu-id="0e226-109">In this case, the mapping schema must be stored in the directory (or one of its subdirectories, in which case a relative path is specified as the value of the `mapping-schema` attribute in the template) associated with template file.</span></span>  
  
-   <span data-ttu-id="0e226-110">Créez une application de test qui utilise des extensions SQLXML pour ADO pour exécuter des requêtes.</span><span class="sxs-lookup"><span data-stu-id="0e226-110">Create a test application that uses SQLXML extensions for ADO to execute queries.</span></span> <span data-ttu-id="0e226-111">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="0e226-111">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="0e226-112">Dans tous les exemples de cette section, les requêtes XPath sont spécifiées dans un modèle et le modèle est exécuté à l'aide d'ADO.</span><span class="sxs-lookup"><span data-stu-id="0e226-112">In all the examples in this section, for illustration purposes, the XPath queries are specified in a template and the template is executed using ADO.</span></span> <span data-ttu-id="0e226-113">Par conséquent, vous devez utiliser le fichier de schéma de mappage SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="0e226-113">Therefore, you must use the following mapping schema file, SampleSchema1.xml.</span></span> <span data-ttu-id="0e226-114">Enregistrez ce fichier dans le répertoire où vos modèles sont stockés.</span><span class="sxs-lookup"><span data-stu-id="0e226-114">Save this file in the directory where your templates are stored.</span></span>  
  
## <a name="sample-annotated-xsd-schema-sampleschema1xml"></a><span data-ttu-id="0e226-115">Exemple de schéma XSD annoté (SampleSchema1.xml)</span><span class="sxs-lookup"><span data-stu-id="0e226-115">Sample Annotated XSD Schema (SampleSchema1.xml)</span></span>  
  
```  
<?xml version="1.0"?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:appinfo>  
      <sql:relationship name="CustOrders"  
                        parent="Sales.Customer"  
                        parent-key="CustomerID"  
                        child="Sales.SalesOrderHeader"  
                        child-key="CustomerID" />  
      <sql:relationship name="OrderOrderDetail"  
                        parent="Sales.SalesOrderHeader"  
                        parent-key="SalesOrderID"  
                        child="Sales.SalesOrderDetail"  
                        child-key="SalesOrderID" />  
    </xsd:appinfo>  
  </xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" type="CustomerType" />  
  
  <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"  
                     sql:relationship="CustOrders" />  
     </xsd:sequence>  
     <xsd:attribute name="CustomerID" type="xsd:ID"/>  
     <xsd:attribute name="TerritoryID"/>  
     <xsd:attribute name="AccountNumber"/>  
     <xsd:attribute name="CustomerType"/>  
     <xsd:attribute name="Orders" type="xsd:IDREFS" sql:prefix="Ord-"/>  
  </xsd:complexType>  
  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader" type="OrderType"/>  
  
  <xsd:complexType name="OrderType">  
     <xsd:sequence>  
        <xsd:element name="OrderDetail"   
                     sql:relation="Sales.SalesOrderDetail"  
                     sql:relationship="OrderOrderDetail" />  
     </xsd:sequence>  
     <xsd:attribute name="SalesOrderID" type="xsd:ID" sql:prefix="Ord-"/>  
     <xsd:attribute name="SalesPersonID"/>  
     <xsd:attribute name="OrderDate"/>  
     <xsd:attribute name="DueDate"/>  
     <xsd:attribute name="ShipDate"/>  
  </xsd:complexType>  
  
  <xsd:element name="OrderDetail" sql:relation="Sales.SalesOrderDetail" type="OrderDetailType"/>  
  
  <xsd:complexType name="OrderDetailType">  
    <xsd:attribute name="ProductID" type="xsd:IDREF"/>  
    <xsd:attribute name="UnitPrice"/>  
    <xsd:attribute name="OrderQty"/>  
    <xsd:attribute name="UnitPriceDiscount"/>  
  </xsd:complexType>  
  
  <xsd:element name="UnitPriceDiscount" sql:relation="Sales.SalesOrderDetail" type="DiscountType"/>  
  
  <xsd:complexType name="DiscountType">  
    <xsd:simpleContent>  
       <xsd:extension base="xsd:string">  
          <xsd:anyAttribute namespace="##other" processContents="lax"/>  
       </xsd:extension>  
    </xsd:simpleContent>  
  </xsd:complexType>  
  
  <xsd:element name="Contact" sql:relation="Person.Contact" type="ContactType"/>  
  
  <xsd:complexType name="ContactType">  
    <xsd:attribute name="ContactID"/>  
    <xsd:attribute name="LastName"/>  
    <xsd:attribute name="FirstName"/>  
    <xsd:attribute name="Title"/>  
  </xsd:complexType>  
  
</xsd:schema>  
```  
  
  
