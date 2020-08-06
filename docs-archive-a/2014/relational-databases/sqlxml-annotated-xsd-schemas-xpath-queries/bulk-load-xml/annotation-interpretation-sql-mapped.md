---
title: 'SQL : mappé (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- mapped annotation
- element mapping [SQLXML], XML Bulk Load
- attribute mapping [SQLXML], XML Bulk Load
- overflow data [SQLXML]
- sql:mapped
- column mapping [SQLXML]
ms.assetid: 7042741e-ce4d-4912-9c4a-d77194a028fc
author: rothja
ms.author: jroth
ms.openlocfilehash: 2cbccf271e069cd87860af672fed6c4bab462b41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605333"
---
# <a name="sqlmapped-sqlxml-40"></a><span data-ttu-id="a0368-102">sql:mapped (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="a0368-102">sql:mapped (SQLXML 4.0)</span></span>
  <span data-ttu-id="a0368-103">Le chargement en masse XML traite l' `sql:mapped` annotation dans le schéma XSD comme prévu, c’est-à-dire que si le schéma de mappage spécifie `sql:mapped="false"` pour un élément ou un attribut, le chargement en masse XML ne tente pas de stocker les données associées dans la colonne correspondante.</span><span class="sxs-lookup"><span data-stu-id="a0368-103">XML Bulk Load processes the `sql:mapped` annotation in the XSD schema as expected-that is, if the mapping schema specifies `sql:mapped="false"` for any element or attribute, XML Bulk Load does not attempt to store the associated data in the corresponding column.</span></span>  
  
 <span data-ttu-id="a0368-104">Le chargement en masse XML ignore les éléments et les attributs qui ne sont pas mappés (soit parce qu'ils ne sont pas décrits dans le schéma, soit parce qu'ils sont annotés dans le schéma XSD avec `sql:mapped="false"`).</span><span class="sxs-lookup"><span data-stu-id="a0368-104">XML Bulk Load ignores elements and attributes that are not mapped (either because they are not described in the schema, or because they are annotated in the XSD schema with `sql:mapped="false"`).</span></span> <span data-ttu-id="a0368-105">Toutes les données non mappées vont dans la colonne de dépassement de capacité, si une telle colonne est spécifiée à l'aide de `sql:overflow-field`.</span><span class="sxs-lookup"><span data-stu-id="a0368-105">All unmapped data goes into the overflow column, if such a column is specified by using `sql:overflow-field`.</span></span>  
  
 <span data-ttu-id="a0368-106">Considérons par exemple ce schéma XSD :</span><span class="sxs-lookup"><span data-stu-id="a0368-106">For example, consider this XSD schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:element name="ROOT" sql:is-constant="1">  
<xsd:complexType>  
<xsd:sequence>  
  <xsd:element name="Customers" sql:relation="Cust"  
                                sql:overflow-field="OverflowColumn" >  
   <xsd:complexType>  
       <xsd:attribute name="CustomerID"  type="xsd:integer" />  
       <xsd:attribute name="CompanyName" type="xsd:string" />  
       <xsd:attribute name="City"        type="xsd:string" />  
       <xsd:attribute name="HomePhone"   type="xsd:string"   
                                       sql:mapped="false" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:sequence>  
</xsd:complexType>  
</xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="a0368-107">Étant donné que l’attribut **HomePhone** spécifie `sql:mapped="false"` , le chargement en masse XML ne mappe pas cet attribut à la colonne correspondante.</span><span class="sxs-lookup"><span data-stu-id="a0368-107">Because the **HomePhone** attribute specifies `sql:mapped="false"`, XML Bulk Load does not map this attribute to the corresponding column.</span></span> <span data-ttu-id="a0368-108">Le schéma XSD identifie une colonne de dépassement (**OverflowColumn**) dans laquelle le chargement en masse XML stocke ces données non consommées.</span><span class="sxs-lookup"><span data-stu-id="a0368-108">The XSD schema identifies an overflow column (**OverflowColumn**) in which XML Bulk Load stores this unconsumed data.</span></span>  
  
### <a name="to-test-a-working-sample"></a><span data-ttu-id="a0368-109">Pour tester un exemple fonctionnel</span><span class="sxs-lookup"><span data-stu-id="a0368-109">To test a working sample</span></span>  
  
1.  <span data-ttu-id="a0368-110">Créez la table suivante dans la base de données **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="a0368-110">Create the following table in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Cust  
              (CustomerID     int         PRIMARY KEY,  
               CompanyName    varchar(20) NOT NULL,  
               City           varchar(20) DEFAULT 'Seattle',  
               OverflowColumn nvarchar(200))  
    GO  
    ```  
  
2.  <span data-ttu-id="a0368-111">Enregistrez le schéma fourni dans cet exemple sous le nom SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="a0368-111">Save the schema that is provided in this example as SampleSchema.xml.</span></span>  
  
3.  <span data-ttu-id="a0368-112">Enregistrez l'exemple de données XML ci-après sous le nom SampleXMLData.xml :</span><span class="sxs-lookup"><span data-stu-id="a0368-112">Save the following sample XML data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>  
      <Customers CustomerID="1111" CompanyName="Sean Chai"   
                 City="NY" HomePhone="111-1111" />  
      <Customers CustomerID="1112" CompanyName="Dont Know"   
                 City="LA" HomePhone="222-2222" />  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="a0368-113">Pour exécuter le chargement en masse XML, enregistrez cet exemple [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) sous le nom Sample.vbs et exécutez-le :</span><span class="sxs-lookup"><span data-stu-id="a0368-113">To execute XML Bulk Load, save and execute this [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) example as Sample.vbs:</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints=True  
    objBL.Execute "c:\SampleSchema.xml", "c:\SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
 <span data-ttu-id="a0368-114">Voici le schéma XDR équivalent :</span><span class="sxs-lookup"><span data-stu-id="a0368-114">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >   
   <ElementType name="ROOT" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
   <ElementType name="Customers" sql:relation="Cust"  
                             sql:overflow-field="OverflowColumn" >  
      <AttributeType name="CustomerID" />  
      <AttributeType name="CompanyName"  />  
      <AttributeType name="City"  />  
      <AttributeType name="HomePhone" />  
      <attribute type="CustomerID"  />  
      <attribute type="CompanyName"  />  
      <attribute type="City" />  
      <attribute type="HomePhone" sql:map-field="0" />  
   </ElementType>  
</Schema>  
```  
  
  
