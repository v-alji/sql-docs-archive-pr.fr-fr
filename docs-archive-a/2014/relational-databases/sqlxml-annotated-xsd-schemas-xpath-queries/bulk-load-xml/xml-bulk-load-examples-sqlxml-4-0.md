---
title: Exemples de chargement en masse XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- overflow-field annotation
- ConnectionCommand property
- XMLFragment property
- relationship chains [SQLXML]
- multiple table bulk loading
- examples [SQLXML], XML Bulk Load
- overflow data [SQLXML]
- sql:datatype
- transaction mode [SQLXML]
- CheckConstraints property
- sql:overflow-field
- XML Bulk Load [SQLXML], examples
- TempFilePath property
- datatype annotation
- Transaction property
- KeepIdentity property
- Execute method
- streaming XML data
- xml data type [SQL Server], SQLXML
- bulk load [SQLXML], examples
ms.assetid: 970e4553-b41d-4a12-ad50-0ee65d1f305d
author: rothja
ms.author: jroth
ms.openlocfilehash: c7eaec77ef068efd28c4da65833afa5047b222f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695488"
---
# <a name="xml-bulk-load-examples-sqlxml-40"></a><span data-ttu-id="33c24-102">Exemples de chargement en masse XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="33c24-102">XML Bulk Load Examples (SQLXML 4.0)</span></span>
  <span data-ttu-id="33c24-103">Les exemples suivants illustrent la fonctionnalité de chargement en masse XML dans Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33c24-103">The following examples illustrate the XML Bulk Load functionality in Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="33c24-104">Chaque exemple fournit un schéma XSD et son schéma XDR équivalent.</span><span class="sxs-lookup"><span data-stu-id="33c24-104">Each example provides an XSD schema and its equivalent XDR schema.</span></span>  
  
## <a name="bulk-loader-script-validateandbulkloadvbs"></a><span data-ttu-id="33c24-105">Script de chargement en masse (ValidateAndBulkload.vbs)</span><span class="sxs-lookup"><span data-stu-id="33c24-105">Bulk Loader Script (ValidateAndBulkload.vbs)</span></span>  
 <span data-ttu-id="33c24-106">Le script suivant, écrit en [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript), charge un document XML dans le DOM XML, le valide par rapport à un schéma et, si le document est valide, exécute un chargement en masse XML pour charger le code XML dans une [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] table.</span><span class="sxs-lookup"><span data-stu-id="33c24-106">The following script, written in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript), loads an XML document into the XML DOM; validates it against a schema; and, if the document is valid, executes an XML bulk load to load the XML into a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="33c24-107">Ce script peut être utilisé avec chacun des exemples individuels qui s'y rapportent plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="33c24-107">This script can be used with each of the individual examples that refer to it later in this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="33c24-108">Le chargement en masse XML n'émet pas d'avertissement ou d'erreur si aucun contenu n'est téléchargé à partir du fichier de données.</span><span class="sxs-lookup"><span data-stu-id="33c24-108">XML Bulk Load does not throw a warning or an error if no content is uploaded from the data file.</span></span> <span data-ttu-id="33c24-109">Par conséquent, il est conseillé de valider votre fichier de données XML avant d'exécuter une opération de chargement en masse.</span><span class="sxs-lookup"><span data-stu-id="33c24-109">Therefore, it is a good practice to validate your XML data file prior to executing a bulk load operation.</span></span>  
  
```  
Dim FileValid  
  
set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
objBL.ConnectionString = "provider=SQLOLEDB;data source=MyServer;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
  
'Validate the data file prior to bulkload  
Dim sOutput   
sOutput = ValidateFile("SampleXMLData.xml", "", "SampleSchema.xml")  
WScript.Echo sOutput  
  
If FileValid Then  
   ' Check constraints and initiate transaction (if needed)  
   ' objBL.CheckConstraints = True  
   ' objBL.Transaction=True  
  'Execute XML bulkload using file.  
  objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
  set objBL=Nothing  
End If  
  
Function ValidateFile(strXmlFile,strUrn,strXsdFile)  
  
   ' Create a schema cache and add SampleSchema.xml to it.  
   Dim xs, fso, sAppPath  
   Set fso = CreateObject("Scripting.FileSystemObject")   
   Set xs = CreateObject("MSXML2.XMLSchemaCache.6.0")  
   sAppPath = fso.GetFolder(".")   
   xs.Add strUrn, sAppPath & "\" & strXsdFile  
  
   ' Create an XML DOMDocument object.  
   Dim xd   
   Set xd = CreateObject("MSXML2.DOMDocument.6.0")  
  
   ' Assign the schema cache to the DOM document.  
   ' schemas collection.  
   Set xd.schemas = xs  
  
   ' Load XML document as DOM document.  
   xd.async = False  
   xd.Load sAppPath & "\" & strXmlFile  
  
   ' Return validation results in message to the user.  
   If xd.parseError.errorCode <> 0 Then  
        ValidateFile = "Validation failed on " & _  
             strXmlFile & vbCrLf & _  
             "=======" & vbCrLf & _  
             "Reason: " & xd.parseError.reason & _  
             vbCrLf & "Source: " & _  
             xd.parseError.srcText & _  
             vbCrLf & "Line: " & _  
             xd.parseError.Line & vbCrLf  
             FileValid = False  
    Else  
        ValidateFile = "Validation succeeded for " & _  
             strXmlFile & vbCrLf & _  
             "========" & _  
             vbCrLf & "Contents to be bulkloaded" & vbCrLf  
             FileValid = True  
    End If  
End Function  
```  
  
## <a name="a-bulk-loading-xml-in-a-table"></a><span data-ttu-id="33c24-110">R.</span><span class="sxs-lookup"><span data-stu-id="33c24-110">A.</span></span> <span data-ttu-id="33c24-111">Chargement en masse XML dans une table</span><span class="sxs-lookup"><span data-stu-id="33c24-111">Bulk loading XML in a table</span></span>  
 <span data-ttu-id="33c24-112">Cet exemple établit une connexion à l’instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] spécifiée dans la propriété ConnectionString (MyServer).</span><span class="sxs-lookup"><span data-stu-id="33c24-112">This example establishes a connection to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is specified in the ConnectionString property (MyServer).</span></span> <span data-ttu-id="33c24-113">L’exemple spécifie également la propriété ErrorLogFile.</span><span class="sxs-lookup"><span data-stu-id="33c24-113">The example also specifies the ErrorLogFile property.</span></span> <span data-ttu-id="33c24-114">Par conséquent, la sortie d'erreur est enregistrée dans le fichier spécifié (« C:\error.log »), dont l'emplacement peut également être modifié.</span><span class="sxs-lookup"><span data-stu-id="33c24-114">Therefore, the error output is saved in the specified file ("C:\error.log"), which you might also decide to change to a different location.</span></span> <span data-ttu-id="33c24-115">Notez également que la méthode Execute a comme paramètres le fichier de schéma de mappage (SampleSchema.xml) et le fichier de données XML (SampleXMLData.xml).</span><span class="sxs-lookup"><span data-stu-id="33c24-115">Notice also that the Execute method has as its parameters both the mapping schema file (SampleSchema.xml) and the XML data file (SampleXMLData.xml).</span></span> <span data-ttu-id="33c24-116">Lorsque le chargement en masse s’exécute, la table Cust que vous avez créée dans la base de données **tempdb** contient de nouveaux enregistrements basés sur le contenu du fichier de données XML.</span><span class="sxs-lookup"><span data-stu-id="33c24-116">When the bulk load executes, the Cust table you have created in **tempdb** database will contain new records based upon the contents of the XML data file.</span></span>  
  
#### <a name="to-test-a-sample-bulk-load"></a><span data-ttu-id="33c24-117">Pour tester un exemple de chargement en masse</span><span class="sxs-lookup"><span data-stu-id="33c24-117">To test a sample bulk load</span></span>  
  
1.  <span data-ttu-id="33c24-118">Créez cette table :</span><span class="sxs-lookup"><span data-stu-id="33c24-118">Create this table:</span></span>  
  
    ```  
    CREATE TABLE Cust(CustomerID  int PRIMARY KEY,  
                      CompanyName varchar(20),  
                      City        varchar(20));  
    GO  
    ```  
  
2.  <span data-ttu-id="33c24-119">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="33c24-119">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="33c24-120">Ajoutez à ce fichier le schéma XSD suivant :</span><span class="sxs-lookup"><span data-stu-id="33c24-120">To this file, add the following XSD schema:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
       <xsd:element name="ROOT" sql:is-constant="1" >  
         <xsd:complexType>  
           <xsd:sequence>  
             <xsd:element name="Customers" sql:relation="Cust" maxOccurs="unbounded">  
               <xsd:complexType>  
                 <xsd:sequence>  
                   <xsd:element name="CustomerID"  type="xsd:integer" />  
                   <xsd:element name="CompanyName" type="xsd:string" />  
                   <xsd:element name="City"        type="xsd:string" />  
                 </xsd:sequence>  
               </xsd:complexType>  
             </xsd:element>  
           </xsd:sequence>  
          </xsd:complexType>  
         </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="33c24-121">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="33c24-121">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="33c24-122">Ajoutez à ce fichier le document XML suivant :</span><span class="sxs-lookup"><span data-stu-id="33c24-122">To this file, add the following XML document:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Sean Chai</CompanyName>  
        <City>New York</City>  
      </Customers>  
      <Customers>  
        <CustomerID>1112</CustomerID>  
        <CompanyName>Tom Johnston</CompanyName>  
         <City>Los Angeles</City>  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Institute of Art</CompanyName>  
        <City>Chicago</City>  
      </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="33c24-123">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="33c24-123">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="33c24-124">Ajoutez à ce fichier le code VBScript fourni ci-dessus au début de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="33c24-124">To this file, add the VBScript code that is provided above at the beginning of this topic.</span></span> <span data-ttu-id="33c24-125">Modifiez la chaîne de connexion pour fournir le nom de serveur approprié.</span><span class="sxs-lookup"><span data-stu-id="33c24-125">Modify the connection string to provide the appropriate server name.</span></span> <span data-ttu-id="33c24-126">Spécifiez le chemin d’accès approprié pour les fichiers qui sont spécifiés en tant que paramètres à la méthode Execute.</span><span class="sxs-lookup"><span data-stu-id="33c24-126">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
5.  <span data-ttu-id="33c24-127">Exécutez le code VBScript.</span><span class="sxs-lookup"><span data-stu-id="33c24-127">Execute the VBScript code.</span></span> <span data-ttu-id="33c24-128">La fonctionnalité de chargement en masse XML charge les données XML dans la table Cust.</span><span class="sxs-lookup"><span data-stu-id="33c24-128">XML Bulk Load loads the XML into the Cust table.</span></span>  
  
 <span data-ttu-id="33c24-129">Voici le schéma XDR équivalent :</span><span class="sxs-lookup"><span data-stu-id="33c24-129">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >   
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="ROOT" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers"  sql:relation="Cust" >  
      <element type="CustomerID"  sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City"        sql:field="City" />  
  
   </ElementType>  
</Schema>  
```  
  
## <a name="b-bulk-loading-xml-data-in-multiple-tables"></a><span data-ttu-id="33c24-130">B.</span><span class="sxs-lookup"><span data-stu-id="33c24-130">B.</span></span> <span data-ttu-id="33c24-131">Chargement en masse des données XML dans plusieurs tables</span><span class="sxs-lookup"><span data-stu-id="33c24-131">Bulk loading XML data in multiple tables</span></span>  
 <span data-ttu-id="33c24-132">Dans cet exemple, le document XML se compose des **\<Customer>** **\<Order>** éléments et.</span><span class="sxs-lookup"><span data-stu-id="33c24-132">In this example, the XML document consists of the **\<Customer>** and **\<Order>** elements.</span></span>  
  
```  
<ROOT>  
  <Customers>  
    <CustomerID>1111</CustomerID>  
    <CompanyName>Sean Chai</CompanyName>  
    <City>NY</City>  
    <Order OrderID="1" />  
    <Order OrderID="2" />  
  </Customers>  
  <Customers>  
    <CustomerID>1112</CustomerID>  
    <CompanyName>Tom Johnston</CompanyName>  
     <City>LA</City>    
    <Order OrderID="3" />  
  </Customers>  
  <Customers>  
    <CustomerID>1113</CustomerID>  
    <CompanyName>Institute of Art</CompanyName>  
    <Order OrderID="4" />  
  </Customers>  
</ROOT>  
```  
  
 <span data-ttu-id="33c24-133">Cet exemple charge en masse les données XML dans deux tables, **cust** et **CustOrder**:</span><span class="sxs-lookup"><span data-stu-id="33c24-133">This example bulk loads the XML data into two tables, **Cust** and **CustOrder**:</span></span>  
  
```  
Cust(CustomerID, CompanyName, City)  
CustOrder(OrderID, CustomerID)  
```  
  
 <span data-ttu-id="33c24-134">Le schéma XSD suivant définit la vue XML de ces tables.</span><span class="sxs-lookup"><span data-stu-id="33c24-134">The following XSD schema defines the XML view of these tables.</span></span> <span data-ttu-id="33c24-135">Le schéma spécifie la relation parent-enfant entre **\<Customer>** les **\<Order>** éléments et.</span><span class="sxs-lookup"><span data-stu-id="33c24-135">The schema specifies the parent-child relationship between the **\<Customer>** and **\<Order>** elements.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
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
  <xsd:element name="ROOT" sql:is-constant="1" >  
    <xsd:complexType>  
      <xsd:sequence>  
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
      </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="33c24-136">Le chargement en masse XML utilise la relation clé primaire/clé étrangère spécifiée ci-dessus entre les **\<Cust>** **\<CustOrder>** éléments et pour charger en masse les données dans les deux tables.</span><span class="sxs-lookup"><span data-stu-id="33c24-136">XML Bulk Load uses the primary key/foreign key relationship specified above between the **\<Cust>** and **\<CustOrder>** elements to bulk load the data into both tables.</span></span>  
  
#### <a name="to-test-a-sample-bulk-load"></a><span data-ttu-id="33c24-137">Pour tester un exemple de chargement en masse</span><span class="sxs-lookup"><span data-stu-id="33c24-137">To test a sample bulk load</span></span>  
  
1.  <span data-ttu-id="33c24-138">Créez deux tables dans la base de données **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="33c24-138">Create two tables in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust(  
           CustomerID  int PRIMARY KEY,  
           CompanyName varchar(20),  
           City        varchar(20));  
    CREATE TABLE CustOrder(        OrderID     int PRIMARY KEY,   
            CustomerID int FOREIGN KEY REFERENCES Cust(CustomerID));  
    ```  
  
2.  <span data-ttu-id="33c24-139">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="33c24-139">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="33c24-140">Ajoutez le schéma XSD fourni dans cet exemple au fichier.</span><span class="sxs-lookup"><span data-stu-id="33c24-140">Add the XSD schema that is provided in this example to the file.</span></span>  
  
3.  <span data-ttu-id="33c24-141">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom SampleData.xml.</span><span class="sxs-lookup"><span data-stu-id="33c24-141">Create a file in your preferred text or XML editor, and save it as SampleData.xml.</span></span> <span data-ttu-id="33c24-142">Ajoutez le document XML fourni précédemment dans cet exemple au fichier.</span><span class="sxs-lookup"><span data-stu-id="33c24-142">Add the XML document that was provided earlier in this example to the file.</span></span>  
  
4.  <span data-ttu-id="33c24-143">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="33c24-143">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="33c24-144">Ajoutez à ce fichier le code VBScript fourni ci-dessus au début de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="33c24-144">To this file, add the VBScript code that is provided above at the beginning of this topic.</span></span> <span data-ttu-id="33c24-145">Modifiez la chaîne de connexion pour fournir le nom de serveur et le nom de base de données appropriés.</span><span class="sxs-lookup"><span data-stu-id="33c24-145">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="33c24-146">Spécifiez le chemin d’accès approprié pour les fichiers qui sont spécifiés en tant que paramètres à la méthode Execute.</span><span class="sxs-lookup"><span data-stu-id="33c24-146">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
5.  <span data-ttu-id="33c24-147">Exécutez le code VBScript ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="33c24-147">Execute the VBScript code above.</span></span> <span data-ttu-id="33c24-148">La fonctionnalité de chargement en masse XML charge le document XML dans les tables Cust et CustOrder.</span><span class="sxs-lookup"><span data-stu-id="33c24-148">XML Bulk Load loads the XML document into the Cust and CustOrder tables.</span></span>  
  
 <span data-ttu-id="33c24-149">Voici le schéma XDR équivalent :</span><span class="sxs-lookup"><span data-stu-id="33c24-149">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >   
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="ROOT" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust" >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
<sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
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
  
## <a name="c-using-chain-relationships-in-the-schema-to-bulk-load-xml"></a><span data-ttu-id="33c24-150">C.</span><span class="sxs-lookup"><span data-stu-id="33c24-150">C.</span></span> <span data-ttu-id="33c24-151">Utilisation des relations de chaîne dans le schéma pour charger en masse des données XML</span><span class="sxs-lookup"><span data-stu-id="33c24-151">Using chain relationships in the schema to bulk load XML</span></span>  
 <span data-ttu-id="33c24-152">Cet exemple illustre la façon dont la relation M:N spécifiée dans le schéma de mappage est utilisée par la fonctionnalité de chargement en masse XML pour charger des données dans une table qui représente une relation M:N.</span><span class="sxs-lookup"><span data-stu-id="33c24-152">This example illustrates how the M:N relationship that is specified in the mapping schema is used by XML Bulk Load to load data in a table that represents an M:N relationship.</span></span>  
  
 <span data-ttu-id="33c24-153">Considérons par exemple ce schéma XSD :</span><span class="sxs-lookup"><span data-stu-id="33c24-153">For example, consider this XSD schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="OrderOD"  
          parent="Ord"  
          parent-key="OrderID"  
          child="OrderDetail"  
          child-key="OrderID" />  
  
    <sql:relationship name="ODProduct"  
          parent="OrderDetail"  
          parent-key="ProductID"  
          child="Product"  
          child-key="ProductID"   
          inverse="true"/>  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="ROOT" sql:is-constant="1" >  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Ord"   
                     sql:key-fields="OrderID" >  
          <xsd:complexType>  
            <xsd:sequence>  
             <xsd:element name="Product"  
                          sql:relation="Product"   
                          sql:key-fields="ProductID"  
                          sql:relationship="OrderOD ODProduct">  
               <xsd:complexType>  
                 <xsd:attribute name="ProductID" type="xsd:int" />  
                 <xsd:attribute name="ProductName" type="xsd:string" />  
               </xsd:complexType>  
             </xsd:element>  
           </xsd:sequence>  
           <xsd:attribute name="OrderID"   type="xsd:integer" />   
           <xsd:attribute name="CustomerID"   type="xsd:string" />  
         </xsd:complexType>  
       </xsd:element>  
      </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="33c24-154">Le schéma spécifie un **\<Order>** élément avec un **\<Product>** élément enfant.</span><span class="sxs-lookup"><span data-stu-id="33c24-154">The schema specifies an **\<Order>** element with a **\<Product>** child element.</span></span> <span data-ttu-id="33c24-155">L' **\<Order>** élément est mappé à la table Ord et l' **\<Product>** élément est mappé à la table Product de la base de données.</span><span class="sxs-lookup"><span data-stu-id="33c24-155">The **\<Order>** element maps to Ord table and the **\<Product>** element maps to the Product table in the database.</span></span> <span data-ttu-id="33c24-156">La relation de chaîne spécifiée sur l' **\<Product>** élément identifie une relation M :N représentée par la table OrderDetail.</span><span class="sxs-lookup"><span data-stu-id="33c24-156">The chain relationship specified on the **\<Product>** element identifies a M:N relationship represented by the OrderDetail table.</span></span> <span data-ttu-id="33c24-157">(Une commande peut inclure de nombreux produits, et un produit peut être inclus dans de nombreuses commandes.)</span><span class="sxs-lookup"><span data-stu-id="33c24-157">(An order can include many products, and a product can be included in many orders.)</span></span>  
  
 <span data-ttu-id="33c24-158">Lorsque vous chargez en masse un document XML avec ce schéma, les enregistrements sont ajoutés aux tables Ord, Product et OrderDetail.</span><span class="sxs-lookup"><span data-stu-id="33c24-158">When you are bulk loading an XML document with this schema, records are added to the Ord, Product, and OrderDetail tables.</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="33c24-159">Pour tester un exemple fonctionnel</span><span class="sxs-lookup"><span data-stu-id="33c24-159">To test a working sample</span></span>  
  
1.  <span data-ttu-id="33c24-160">Créez trois tables :</span><span class="sxs-lookup"><span data-stu-id="33c24-160">Create three tables:</span></span>  
  
    ```  
    CREATE TABLE Ord (  
             OrderID     int  PRIMARY KEY,  
             CustomerID  varchar(5));  
    GO  
    CREATE TABLE Product (  
             ProductID   int PRIMARY KEY,  
             ProductName varchar(20));  
    GO  
    CREATE TABLE OrderDetail (  
           OrderID     int FOREIGN KEY REFERENCES Ord(OrderID),  
           ProductID   int FOREIGN KEY REFERENCES Product(ProductID),  
                       CONSTRAINT OD_key PRIMARY KEY (OrderID, ProductID));  
    GO  
    ```  
  
2.  <span data-ttu-id="33c24-161">Enregistrez le schéma fourni ci-dessus dans cet exemple sous le nom SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="33c24-161">Save the schema that is provided above in this example as SampleSchema.xml.</span></span>  
  
3.  <span data-ttu-id="33c24-162">Enregistrez l'exemple de données XML ci-après sous le nom SampleXMLData.xml :</span><span class="sxs-lookup"><span data-stu-id="33c24-162">Save the following sample XML data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>    
      <Order OrderID="1" CustomerID="ALFKI">  
        <Product ProductID="1" ProductName="Chai" />  
        <Product ProductID="2" ProductName="Chang" />  
      </Order>  
      <Order OrderID="2" CustomerID="ANATR">  
        <Product ProductID="3" ProductName="Aniseed Syrup" />  
        <Product ProductID="4" ProductName="Gumbo Mix" />  
      </Order>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="33c24-163">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="33c24-163">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="33c24-164">Ajoutez à ce fichier le code VBScript fourni ci-dessus au début de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="33c24-164">To this file, add the VBScript code that is provided above at the beginning of this topic.</span></span> <span data-ttu-id="33c24-165">Modifiez la chaîne de connexion pour fournir le nom de serveur et le nom de base de données appropriés.</span><span class="sxs-lookup"><span data-stu-id="33c24-165">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="33c24-166">Supprimez les marques de commentaire des lignes suivantes dans le code source de cet exemple.</span><span class="sxs-lookup"><span data-stu-id="33c24-166">Uncomment the following lines from the source code for this example.</span></span>  
  
    ```  
    objBL.CheckConstraints = True  
    objBL.Transaction=True  
    ```  
  
5.  <span data-ttu-id="33c24-167">Exécutez le code VBScript.</span><span class="sxs-lookup"><span data-stu-id="33c24-167">Execute the VBScript code.</span></span> <span data-ttu-id="33c24-168">La fonctionnalité de chargement en masse XML charge le document XML dans les tables Ord et Product.</span><span class="sxs-lookup"><span data-stu-id="33c24-168">XML Bulk Load loads the XML document into the Ord and Product tables.</span></span>  
  
## <a name="d-bulk-loading-in-identity-type-columns"></a><span data-ttu-id="33c24-169">D.</span><span class="sxs-lookup"><span data-stu-id="33c24-169">D.</span></span> <span data-ttu-id="33c24-170">Chargement en masse dans des colonnes de type identity</span><span class="sxs-lookup"><span data-stu-id="33c24-170">Bulk loading in identity type columns</span></span>  
 <span data-ttu-id="33c24-171">Cet exemple montre comment la fonctionnalité de chargement en masse gère les colonnes de type identity.</span><span class="sxs-lookup"><span data-stu-id="33c24-171">This example illustrates how bulk load handles identity type columns.</span></span> <span data-ttu-id="33c24-172">Dans cet exemple, les données sont chargées en masse dans trois tables (Ord, Product et OrderDetail).</span><span class="sxs-lookup"><span data-stu-id="33c24-172">In the example, data is bulk loaded into three tables (Ord, Product, and OrderDetail).</span></span>  
  
 <span data-ttu-id="33c24-173">Dans les tableaux suivants :</span><span class="sxs-lookup"><span data-stu-id="33c24-173">In these tables:</span></span>  
  
-   <span data-ttu-id="33c24-174">OrderID dans la table Ord est une colonne de type identity.</span><span class="sxs-lookup"><span data-stu-id="33c24-174">OrderID in the Ord table is an identity type column</span></span>  
  
-   <span data-ttu-id="33c24-175">ProductID dans la table Product est une colonne de type identity.</span><span class="sxs-lookup"><span data-stu-id="33c24-175">ProductID in the Product table is an identity type column.</span></span>  
  
-   <span data-ttu-id="33c24-176">Les colonnes OrderID et ProductID dans la table OrderDetail sont des colonnes de clés étrangères qui font référence aux colonnes de clés primaires correspondantes dans les tables Ord et Product.</span><span class="sxs-lookup"><span data-stu-id="33c24-176">OrderID and ProductID columns in the OrderDetail are foreign key columns referring to corresponding primary key columns in the Ord and Product tables.</span></span>  
  
 <span data-ttu-id="33c24-177">Voici les schémas de table de cet exemple :</span><span class="sxs-lookup"><span data-stu-id="33c24-177">The following are the table schemas for this example:</span></span>  
  
```  
Ord (OrderID, CustomerID)  
Product (ProductID, ProductName)  
OrderDetail (OrderID, ProductID)  
```  
  
 <span data-ttu-id="33c24-178">Dans cet exemple de chargement en masse XML, la propriété KeepIdentity du modèle objet BulkLoad a la valeur false.</span><span class="sxs-lookup"><span data-stu-id="33c24-178">In this example of XML Bulk Load, the KeepIdentity property of the BulkLoad object model is set to false.</span></span> <span data-ttu-id="33c24-179">Par conséquent, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] génère des valeurs d'identité pour les colonnes ProductID et OrderID des tables Product et Ord, respectivement (toutes les valeurs fournies dans les documents à charger en masse sont ignorées).</span><span class="sxs-lookup"><span data-stu-id="33c24-179">Therefore, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] generates identity values for the ProductID and OrderID columns in the Product and Ord tables, respectively (any values provided in the documents to be bulk loaded are ignored).</span></span>  
  
 <span data-ttu-id="33c24-180">Dans ce cas, la fonctionnalité de chargement en masse XML identifie la relation clé primaire/clé étrangère qui existe entre les tables.</span><span class="sxs-lookup"><span data-stu-id="33c24-180">In this case, XML Bulk Load identifies the primary key/foreign key relationship among tables.</span></span> <span data-ttu-id="33c24-181">La fonctionnalité de chargement en masse insère au préalable des enregistrements dans les tables ayant la clé primaire, puis propage la valeur d'identité générée par [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] aux tables ayant des colonnes de clés étrangères.</span><span class="sxs-lookup"><span data-stu-id="33c24-181">Bulk Load first inserts records in the tables with the primary key, then propagates the identity value generated by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to the tables with foreign key columns.</span></span> <span data-ttu-id="33c24-182">Dans l'exemple suivant, la fonctionnalité de chargement en masse XML insère des données dans les tables dans cet ordre :</span><span class="sxs-lookup"><span data-stu-id="33c24-182">In the following example, XML Bulk Load inserts data in tables in this order:</span></span>  
  
1.  <span data-ttu-id="33c24-183">Produit</span><span class="sxs-lookup"><span data-stu-id="33c24-183">Product</span></span>  
  
2.  <span data-ttu-id="33c24-184">Ord</span><span class="sxs-lookup"><span data-stu-id="33c24-184">Ord</span></span>  
  
3.  <span data-ttu-id="33c24-185">OrderDetail</span><span class="sxs-lookup"><span data-stu-id="33c24-185">OrderDetail</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="33c24-186">Pour propager les valeurs d'identité générées dans les tables Products et Orders, la logique de traitement nécessite que la fonctionnalité de chargement en masse XML effectue le suivi de ces valeurs pour une insertion ultérieure dans la table OrderDetails.</span><span class="sxs-lookup"><span data-stu-id="33c24-186">In order to propagate identity values generated in the Products and Orders tables, the processing logic requires XML Bulk Load to keep track of these values for later insertion into the OrderDetails table.</span></span> <span data-ttu-id="33c24-187">Pour ce faire, la fonctionnalité de chargement en masse XML crée des tables intermédiaires, remplit les données de ces tables, puis les supprime ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="33c24-187">To do that, XML Bulk Load creates intermediate tables, populates the data in these tables, and later removes them.</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="33c24-188">Pour tester un exemple fonctionnel</span><span class="sxs-lookup"><span data-stu-id="33c24-188">To test a working sample</span></span>  
  
1.  <span data-ttu-id="33c24-189">Créez les tables suivantes :</span><span class="sxs-lookup"><span data-stu-id="33c24-189">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Ord (  
             OrderID     int identity(1,1)  PRIMARY KEY,  
             CustomerID  varchar(5));  
    GO  
    CREATE TABLE Product (  
             ProductID   int identity(1,1) PRIMARY KEY,  
             ProductName varchar(20));  
    GO  
    CREATE TABLE OrderDetail (  
           OrderID     int FOREIGN KEY REFERENCES Ord(OrderID),  
           ProductID   int FOREIGN KEY REFERENCES Product(ProductID),  
                       CONSTRAINT OD_key PRIMARY KEY (OrderID, ProductID));  
    GO  
    ```  
  
2.  <span data-ttu-id="33c24-190">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="33c24-190">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="33c24-191">Ajoutez ce schéma XSD à ce fichier.</span><span class="sxs-lookup"><span data-stu-id="33c24-191">Add this XSD schema to this file.</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
     <xsd:annotation>  
       <xsd:appinfo>  
        <sql:relationship name="OrderOD"  
              parent="Ord"  
              parent-key="OrderID"  
              child="OrderDetail"  
              child-key="OrderID" />  
        <sql:relationship name="ODProduct"  
              parent="OrderDetail"  
              parent-key="ProductID"  
              child="Product"  
              child-key="ProductID"   
              inverse="true"/>  
       </xsd:appinfo>  
     </xsd:annotation>  
  
      <xsd:element name="Order" sql:relation="Ord"   
                                sql:key-fields="OrderID" >  
       <xsd:complexType>  
         <xsd:sequence>  
            <xsd:element name="Product" sql:relation="Product"   
                         sql:key-fields="ProductID"  
                         sql:relationship="OrderOD ODProduct">  
              <xsd:complexType>  
                 <xsd:attribute name="ProductID" type="xsd:int" />  
                 <xsd:attribute name="ProductName" type="xsd:string" />  
              </xsd:complexType>  
            </xsd:element>  
         </xsd:sequence>  
            <xsd:attribute name="OrderID"   type="xsd:integer" />   
            <xsd:attribute name="CustomerID"   type="xsd:string" />  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="33c24-192">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="33c24-192">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="33c24-193">Ajoutez le document XML suivant :</span><span class="sxs-lookup"><span data-stu-id="33c24-193">Add the following XML document.</span></span>  
  
    ```  
    <ROOT>    
      <Order OrderID="11" CustomerID="ALFKI">  
        <Product ProductID="11" ProductName="Chai" />  
        <Product ProductID="22" ProductName="Chang" />  
      </Order>  
      <Order OrderID="22" CustomerID="ANATR">  
         <Product ProductID="33" ProductName="Aniseed Syrup" />  
        <Product ProductID="44" ProductName="Gumbo Mix" />  
      </Order>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="33c24-194">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="33c24-194">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="33c24-195">Ajoutez le code VBScript suivant à ce fichier.</span><span class="sxs-lookup"><span data-stu-id="33c24-195">To this file, add the following VBScript code.</span></span> <span data-ttu-id="33c24-196">Modifiez la chaîne de connexion pour fournir le nom de serveur et le nom de base de données appropriés.</span><span class="sxs-lookup"><span data-stu-id="33c24-196">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="33c24-197">Spécifiez le chemin d’accès approprié pour les fichiers qui servent de paramètres à la `Execute` méthode.</span><span class="sxs-lookup"><span data-stu-id="33c24-197">Specify the appropriate path for the files that serve as parameters to the `Execute` method.</span></span>  
  
    ```  
    Set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "C:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Transaction = False  
    objBL.KeepIdentity = False  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    Set objBL = Nothing  
    MsgBox "Done."  
    ```  
  
5.  <span data-ttu-id="33c24-198">Exécutez le code VBScript.</span><span class="sxs-lookup"><span data-stu-id="33c24-198">Execute the VBScript code.</span></span> <span data-ttu-id="33c24-199">La fonctionnalité de chargement en masse XML charge les données dans les tables appropriées.</span><span class="sxs-lookup"><span data-stu-id="33c24-199">The XML Bulk Load will load the data into the appropriate tables.</span></span>  
  
## <a name="e-generating-table-schemas-before-bulk-loading"></a><span data-ttu-id="33c24-200">E.</span><span class="sxs-lookup"><span data-stu-id="33c24-200">E.</span></span> <span data-ttu-id="33c24-201">Génération de schémas de table avant le chargement en masse</span><span class="sxs-lookup"><span data-stu-id="33c24-201">Generating table schemas before bulk loading</span></span>  
 <span data-ttu-id="33c24-202">La fonctionnalité de chargement en masse XML peut éventuellement générer les tables, si ces dernières n'existent pas avant le chargement en masse.</span><span class="sxs-lookup"><span data-stu-id="33c24-202">XML Bulk Load can optionally generate the tables if they do not exist before bulk loading.</span></span> <span data-ttu-id="33c24-203">L’attribution de la valeur TRUE à la propriété SchemaGen de l’objet SQLXMLBulkLoad.</span><span class="sxs-lookup"><span data-stu-id="33c24-203">Setting the SchemaGen property of the SQLXMLBulkLoad object to TRUE does this.</span></span> <span data-ttu-id="33c24-204">Vous pouvez également demander le chargement en masse XML pour supprimer les tables existantes et les recréer en affectant à la propriété SGDropTables la valeur TRUE.</span><span class="sxs-lookup"><span data-stu-id="33c24-204">You can also optionally request XML Bulk Load to drop any existing tables and re-create them by setting the SGDropTables property to TRUE.</span></span> <span data-ttu-id="33c24-205">L'exemple VBScript ci-dessous illustre l'utilisation de ces propriétés.</span><span class="sxs-lookup"><span data-stu-id="33c24-205">The following VBScript example illustrates the use of these properties.</span></span>  
  
 <span data-ttu-id="33c24-206">Par ailleurs, cet exemple définit deux propriétés supplémentaires à TRUE :</span><span class="sxs-lookup"><span data-stu-id="33c24-206">Also, this example sets two additional properties to TRUE:</span></span>  
  
-   <span data-ttu-id="33c24-207">CheckConstraints.</span><span class="sxs-lookup"><span data-stu-id="33c24-207">CheckConstraints.</span></span> <span data-ttu-id="33c24-208">La définition de cette propriété à TRUE garantit que les données insérées dans les tables ne violent pas les contraintes spécifiées sur les tables (dans le cas présent, il s'agit des contraintes PRIMARY KEY/FOREIGN KEY spécifiées entre les tables Cust et CustOrder).</span><span class="sxs-lookup"><span data-stu-id="33c24-208">Setting this property to TRUE ensures that the data being inserted into the tables does not violate any constraints that have been specified on the tables (in this case the PRIMARY KEY/FOREIGN KEY constraints specified between the Cust and CustOrder tables).</span></span> <span data-ttu-id="33c24-209">S'il existe une violation de contrainte, le chargement en masse échoue.</span><span class="sxs-lookup"><span data-stu-id="33c24-209">If there is a constraint violation, the bulk load fails.</span></span>  
  
-   <span data-ttu-id="33c24-210">XMLFragment.</span><span class="sxs-lookup"><span data-stu-id="33c24-210">XMLFragment.</span></span> <span data-ttu-id="33c24-211">Cette propriété doit être définie à TRUE, car l'exemple de document XML (source de données) ne contient aucun élément unique, de niveau supérieur (il s'agit par conséquent d'un fragment).</span><span class="sxs-lookup"><span data-stu-id="33c24-211">This property must be set to TRUE because the sample XML document (data source) contains no single, top-level element (and is thus a fragment).</span></span>  
  
 <span data-ttu-id="33c24-212">Code VBScript :</span><span class="sxs-lookup"><span data-stu-id="33c24-212">This is the VBScript code:</span></span>  
  
```  
Dim objBL   
Set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
  
objBL.CheckConstraints=true  
objBL.XMLFragment = True  
objBL.SchemaGen = True  
objBL.SGDropTables = True  
  
objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
Set objBL = Nothing  
```  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="33c24-213">Pour tester un exemple fonctionnel</span><span class="sxs-lookup"><span data-stu-id="33c24-213">To test a working sample</span></span>  
  
1.  <span data-ttu-id="33c24-214">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="33c24-214">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="33c24-215">Ajoutez au fichier le schéma XSD fourni dans l'exemple antérieur, « Utilisation des relations de chaîne dans le schéma pour charger en masse des données XML ».</span><span class="sxs-lookup"><span data-stu-id="33c24-215">Add the XSD schema that is provided in the earlier example, "Using chain relationships in the schema to bulk load XML", to the file.</span></span>  
  
2.  <span data-ttu-id="33c24-216">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="33c24-216">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="33c24-217">Ajoutez au fichier le document XML fourni dans l'exemple antérieur, « Utilisation des relations de chaîne dans le schéma pour charger en masse des données XML ».</span><span class="sxs-lookup"><span data-stu-id="33c24-217">Add the XML document that is provided in the earlier example, "Using chain relationships in the schema to bulk load XML", to the file.</span></span> <span data-ttu-id="33c24-218">Supprimez l' \<ROOT> élément du document (pour en faire un fragment).</span><span class="sxs-lookup"><span data-stu-id="33c24-218">Remove the \<ROOT> element from the document (to make it a fragment).</span></span>  
  
3.  <span data-ttu-id="33c24-219">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="33c24-219">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="33c24-220">Ajoutez le code VBScript de cet exemple à ce fichier.</span><span class="sxs-lookup"><span data-stu-id="33c24-220">To this file, add the VBScript code in this example.</span></span> <span data-ttu-id="33c24-221">Modifiez la chaîne de connexion pour fournir le nom de serveur et le nom de base de données appropriés.</span><span class="sxs-lookup"><span data-stu-id="33c24-221">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="33c24-222">Spécifiez le chemin d’accès approprié pour les fichiers qui sont spécifiés en tant que paramètres à la méthode Execute.</span><span class="sxs-lookup"><span data-stu-id="33c24-222">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
4.  <span data-ttu-id="33c24-223">Exécutez le code VBScript.</span><span class="sxs-lookup"><span data-stu-id="33c24-223">Execute the VBScript code.</span></span> <span data-ttu-id="33c24-224">La fonctionnalité de chargement en masse XML crée les tables nécessaires d'après le schéma de mappage fourni, puis charge en masse les données dans ce dernier.</span><span class="sxs-lookup"><span data-stu-id="33c24-224">The XML Bulk Load creates the necessary tables on the basis of the mapping schema that is provided and bulk loads the data in it.</span></span>  
  
## <a name="f-bulk-loading-from-a-stream"></a><span data-ttu-id="33c24-225">F.</span><span class="sxs-lookup"><span data-stu-id="33c24-225">F.</span></span> <span data-ttu-id="33c24-226">Chargement en masse à partir d'un flux de données</span><span class="sxs-lookup"><span data-stu-id="33c24-226">Bulk loading from a stream</span></span>  
 <span data-ttu-id="33c24-227">La méthode Execute du modèle objet de chargement en masse XML accepte deux paramètres.</span><span class="sxs-lookup"><span data-stu-id="33c24-227">The Execute method of the XML Bulk Load object model takes two parameters.</span></span> <span data-ttu-id="33c24-228">Le premier paramètre est le fichier de schéma de mappage.</span><span class="sxs-lookup"><span data-stu-id="33c24-228">The first parameter is the mapping schema file.</span></span> <span data-ttu-id="33c24-229">Le second paramètre fournit les données XML à charger dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="33c24-229">The second parameter provides the XML data that is to be loaded in the database.</span></span> <span data-ttu-id="33c24-230">Il existe deux façons de passer les données XML à la méthode Execute de chargement en masse XML :</span><span class="sxs-lookup"><span data-stu-id="33c24-230">There are two ways to pass the XML data to the Execute method of XML Bulk Load:</span></span>  
  
-   <span data-ttu-id="33c24-231">Spécifiez le nom de fichier en tant que paramètre.</span><span class="sxs-lookup"><span data-stu-id="33c24-231">Specify the file name as the parameter.</span></span>  
  
-   <span data-ttu-id="33c24-232">Passez un flux qui contient les données XML.</span><span class="sxs-lookup"><span data-stu-id="33c24-232">Pass a stream that contains the XML data.</span></span>  
  
 <span data-ttu-id="33c24-233">Cet exemple montre comment effectuer un chargement en masse à partir d'un flux de données.</span><span class="sxs-lookup"><span data-stu-id="33c24-233">This example illustrates how to bulk load from a stream.</span></span>  
  
 <span data-ttu-id="33c24-234">VBScript exécute au préalable une instruction SELECT pour récupérer les informations du client de la table Customers dans la base de données Northwind.</span><span class="sxs-lookup"><span data-stu-id="33c24-234">VBScript first executes a SELECT statement to retrieve customer information from the Customers table in the Northwind database.</span></span> <span data-ttu-id="33c24-235">Dans la mesure où la clause FOR XML est spécifiée (avec l'option ELEMENTS) dans l'instruction SELECT, la requête retourne un document XML centré sur l'élément de ce formulaire :</span><span class="sxs-lookup"><span data-stu-id="33c24-235">Because the FOR XML clause is specified (with the ELEMENTS option) in the SELECT statement, the query returns an element-centric XML document of this form:</span></span>  
  
```  
<Customer>  
  <CustomerID>..</CustomerID>  
  <CompanyName>..</CompanyName>  
  <City>..</City>  
</Customer>  
...  
```  
  
 <span data-ttu-id="33c24-236">Le script transmet ensuite le XML en tant que flux à la méthode Execute en tant que second paramètre.</span><span class="sxs-lookup"><span data-stu-id="33c24-236">The script then passes the XML as a stream to the Execute method as its second parameter.</span></span> <span data-ttu-id="33c24-237">La méthode Execute charge en masse les données dans la table Cust.</span><span class="sxs-lookup"><span data-stu-id="33c24-237">The Execute method bulk loads the data into the Cust table.</span></span>  
  
 <span data-ttu-id="33c24-238">Étant donné que ce script affecte la valeur TRUE à la propriété SchemaGen et la valeur TRUE à la propriété SGDropTables, le chargement en masse XML crée la table Cust dans la base de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="33c24-238">Because this script sets the SchemaGen property to TRUE and SGDropTables property to TRUE, XML Bulk Load creates the Cust table in the specified database.</span></span> <span data-ttu-id="33c24-239">(Si la table existe déjà, elle est d'abord supprimée puis recréée.)</span><span class="sxs-lookup"><span data-stu-id="33c24-239">(If the table already exists, it first drops the table and then re-creates it.)</span></span>  
  
 <span data-ttu-id="33c24-240">Exemple VBScript :</span><span class="sxs-lookup"><span data-stu-id="33c24-240">This is the VBScript example:</span></span>  
  
```  
Set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
Set objCmd = CreateObject("ADODB.Command")  
Set objConn = CreateObject("ADODB.Connection")  
Set objStrmOut = CreateObject ("ADODB.Stream")  
  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile     = "c:\error.log"  
objBL.CheckConstraints = True  
objBL.SchemaGen        = True  
objBL.SGDropTables     = True  
objBL.XMLFragment      = True  
' Open a connection to the instance of SQL Server to get the source data.  
  
objConn.Open "provider=SQLOLEDB;server=(local);database=tempdb;integrated security=SSPI"  
Set objCmd.ActiveConnection = objConn  
objCmd.CommandText = "SELECT CustomerID, CompanyName, City FROM Customers FOR XML AUTO, ELEMENTS"  
  
' Open the return stream and execute the command.  
Const adCRLF = -1  
Const adExecuteStream = 1024  
objStrmOut.Open  
objStrmOut.LineSeparator = adCRLF  
objCmd.Properties("Output Stream").Value = objStrmOut  
objCmd.Execute , , adExecuteStream  
objStrmOut.Position = 0  
  
' Execute bulk load. Read source XML data from the stream.  
objBL.Execute "SampleSchema.xml", objStrmOut  
  
Set objBL = Nothing  
```  
  
 <span data-ttu-id="33c24-241">Le schéma de mappage XSD suivant fournit les informations nécessaires pour créer la table :</span><span class="sxs-lookup"><span data-stu-id="33c24-241">The following XSD mapping schema provides the necessary information to create the table:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:element name="ROOT" sql:is-constant="true" >  
  <xsd:complexType>  
    <xsd:sequence>  
      <xsd:element ref="Customers"/>  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="Customers" sql:relation="Cust" >  
  <xsd:complexType>  
    <xsd:sequence>  
      <xsd:element name="CustomerID"  
                   type="xsd:string"  
                   sql:datatype="nvarchar(5)"/>  
      <xsd:element name="CompanyName"  
                   type="xsd:string"  
                   sql:datatype="nvarchar(40)"/>  
      <xsd:element name="City"  
                   type="xsd:string"  
                   sql:datatype="nvarchar(40)"/>  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="33c24-242">Voici le schéma XDR équivalent :</span><span class="sxs-lookup"><span data-stu-id="33c24-242">This is equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
    </ElementType>  
</Schema>  
```  
  
### <a name="opening-a-stream-on-an-existing-file"></a><span data-ttu-id="33c24-243">Ouverture d'un flux de données sur un fichier existant</span><span class="sxs-lookup"><span data-stu-id="33c24-243">Opening a Stream on an Existing File</span></span>  
 <span data-ttu-id="33c24-244">Vous pouvez également ouvrir un flux sur un fichier de données XML existant et le transmettre en tant que paramètre à la méthode Execute (au lieu de passer le nom de fichier en tant que paramètre).</span><span class="sxs-lookup"><span data-stu-id="33c24-244">You can also open a stream on an existing XML data file and pass the stream as a parameter to the Execute method (instead of passing the file name as the parameter).</span></span>  
  
 <span data-ttu-id="33c24-245">Voici un exemple Visual Basic de passage d'un flux de données en tant que paramètre :</span><span class="sxs-lookup"><span data-stu-id="33c24-245">This is a Visual Basic example of passing a stream as the parameter:</span></span>  
  
```  
Private Sub Form_Load()  
Dim objBL As New SQLXMLBulkLoad  
Dim objStrm As New ADODB.Stream  
Dim objFileSystem As New Scripting.FileSystemObject  
Dim objFile As Scripting.TextStream  
  
MsgBox "Begin BulkLoad..."  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
objBL.CheckConstraints = True  
objBL.SchemaGen = True  
objBL.SGDropTables = True  
' Here again a stream is specified that contains the source data   
' (instead of the file name). But this is just an illustration.  
' Usually this is useful if you have an XML data   
' stream that is created by some other means that you want to bulk   
' load. This example starts with an XML text file, so it may not be the   
' best to use a stream (you can specify the file name directly).  
' Here you could have specified the file name itself.   
Set objFile = objFileSystem.OpenTextFile("c:\SampleData.xml")  
objStrm.Open  
objStrm.WriteText objFile.ReadAll  
objStrm.Position = 0  
objBL.Execute "c:\SampleSchema.xml", objStrm  
  
Set objBL = Nothing  
MsgBox "Done."  
End Sub  
```  
  
 <span data-ttu-id="33c24-246">Pour tester l'application, utilisez le document XML suivant dans un fichier (SampleData.xml) et le schéma XSD fourni dans cet exemple :</span><span class="sxs-lookup"><span data-stu-id="33c24-246">To test the application, use the following XML document in a file (SampleData.xml) and the XSD schema that is provided in this example:</span></span>  
  
 <span data-ttu-id="33c24-247">Données sources XML (SampleData.xml) :</span><span class="sxs-lookup"><span data-stu-id="33c24-247">This is the XML source data (SampleData.xml):</span></span>  
  
```  
<ROOT>  
  <Customers>  
    <CustomerID>1111</CustomerID>  
    <CompanyName>Hanari Carnes</CompanyName>  
    <City>NY</City>  
    <Order OrderID="1" />  
    <Order OrderID="2" />  
  </Customers>  
  
  <Customers>  
    <CustomerID>1112</CustomerID>  
    <CompanyName>Toms Spezialitten</CompanyName>  
     <City>LA</City>  
    <Order OrderID="3" />  
  </Customers>  
  <Customers>  
    <CustomerID>1113</CustomerID>  
    <CompanyName>Victuailles en stock</CompanyName>  
    <Order CustomerID= "4444" OrderID="4" />  
</Customers>  
</ROOT>  
```  
  
 <span data-ttu-id="33c24-248">Voici le schéma XDR équivalent :</span><span class="sxs-lookup"><span data-stu-id="33c24-248">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
  
    <ElementType name="Order" sql:relation="CustOrder" >  
      <AttributeType name="OrderID" />  
      <AttributeType name="CustomerID" />  
      <attribute type="OrderID" />  
      <attribute type="CustomerID" />  
    </ElementType>  
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
             <sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
                foreign-relation="CustOrder" />  
      </element>  
   </ElementType>  
</Schema>  
```  
  
## <a name="g-bulk-loading-in-overflow-columns"></a><span data-ttu-id="33c24-249">G.</span><span class="sxs-lookup"><span data-stu-id="33c24-249">G.</span></span> <span data-ttu-id="33c24-250">Chargement en masse dans les colonnes de dépassement</span><span class="sxs-lookup"><span data-stu-id="33c24-250">Bulk loading in overflow columns</span></span>  
 <span data-ttu-id="33c24-251">Si le schéma de mappage spécifie une colonne de dépassement via l'annotation `sql:overflow-field`, la fonctionnalité de chargement en masse XML copie toutes les données non consommées du document source vers cette colonne.</span><span class="sxs-lookup"><span data-stu-id="33c24-251">If the mapping schema specifies an overflow column by using the `sql:overflow-field` annotation, XML Bulk Load copies all unconsumed data from the source document into this column.</span></span>  
  
 <span data-ttu-id="33c24-252">Examinez ce schéma XSD :</span><span class="sxs-lookup"><span data-stu-id="33c24-252">Consider this XSD schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
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
  <xsd:element name="Customers" sql:relation="Cust"  
                                sql:overflow-field="OverflowColumn" >  
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
          <xsd:attribute name="CustomerID" type="xsd:integer" />  
         </xsd:complexType>  
       </xsd:element>  
     </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="33c24-253">Le schéma identifie une colonne de dépassement (OverflowColumn) pour la table Cust.</span><span class="sxs-lookup"><span data-stu-id="33c24-253">The schema identifies an overflow column (OverflowColumn) for the Cust table.</span></span> <span data-ttu-id="33c24-254">Par conséquent, toutes les données XML non consommées pour chaque **\<Customer>** élément sont ajoutées à cette colonne.</span><span class="sxs-lookup"><span data-stu-id="33c24-254">As a result, all unconsumed XML data for each **\<Customer>** element is added to this column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="33c24-255">Tous les éléments abstraits (éléments pour lesquels **abstract = "true"** est spécifié) et tous les attributs interdits (les attributs pour lesquels **interdit = "true"** est spécifié) sont considérés comme un dépassement de capacité par le chargement en masse XML et sont ajoutés à la colonne de dépassement de capacité, si elle est spécifiée.</span><span class="sxs-lookup"><span data-stu-id="33c24-255">All abstract elements (elements for which **abstract="true"** is specified) and all prohibited attributes (attributes for which **prohibited="true"** is specified) are considered overflow by XML Bulk Load and are added to the overflow column, if specified.</span></span> <span data-ttu-id="33c24-256">(Sinon, ils sont ignorés.)</span><span class="sxs-lookup"><span data-stu-id="33c24-256">(Otherwise, they are ignored.)</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="33c24-257">Pour tester un exemple fonctionnel</span><span class="sxs-lookup"><span data-stu-id="33c24-257">To test a working sample</span></span>  
  
1.  <span data-ttu-id="33c24-258">Créez deux tables dans la base de données **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="33c24-258">Create two tables in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust (  
                  CustomerID     int         PRIMARY KEY,  
                  CompanyName    varchar(20) NOT NULL,  
                  City           varchar(20) DEFAULT 'Seattle',  
                  OverflowColumn nvarchar(200));  
    GO  
    CREATE TABLE CustOrder (  
                  OrderID    int PRIMARY KEY,  
                  CustomerID int FOREIGN KEY   
                                 REFERENCES Cust(CustomerID));  
    GO  
    ```  
  
2.  <span data-ttu-id="33c24-259">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="33c24-259">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="33c24-260">Ajoutez le schéma XSD fourni dans cet exemple au fichier.</span><span class="sxs-lookup"><span data-stu-id="33c24-260">Add the XSD schema that is provided in this example to the file.</span></span>  
  
3.  <span data-ttu-id="33c24-261">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="33c24-261">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="33c24-262">Ajoutez le document XML suivant au fichier :</span><span class="sxs-lookup"><span data-stu-id="33c24-262">Add the following XML document to the file:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Hanari Carnes</CompanyName>  
        <City><![CDATA[NY]]> </City>  
        <Junk>garbage in overflow</Junk>  
        <Order OrderID="1" />  
        <Order OrderID="2" />  
      </Customers>  
  
      <Customers>  
        <CustomerID>1112</CustomerID>  
        <CompanyName>Toms Spezialitten</CompanyName>  
         <![CDATA[LA]]>   
        <!-- <xyz><address>111 Maple, Seattle</address></xyz>   -->  
        <Order OrderID="3" />  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Victuailles en stock</CompanyName>  
        <Order OrderID="4" />  
    </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="33c24-263">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="33c24-263">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="33c24-264">Ajoutez à ce fichier le code Microsoft Visual Basic Scripting Edition (VBScript) suivant.</span><span class="sxs-lookup"><span data-stu-id="33c24-264">To this file, add the following Microsoft Visual Basic Scripting Edition (VBScript) code.</span></span> <span data-ttu-id="33c24-265">Modifiez la chaîne de connexion pour fournir le nom de serveur et le nom de base de données appropriés.</span><span class="sxs-lookup"><span data-stu-id="33c24-265">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="33c24-266">Spécifiez le chemin d’accès approprié pour les fichiers qui sont spécifiés en tant que paramètres à la méthode Execute.</span><span class="sxs-lookup"><span data-stu-id="33c24-266">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
5.  <span data-ttu-id="33c24-267">Exécutez le code VBScript.</span><span class="sxs-lookup"><span data-stu-id="33c24-267">Execute the VBScript code.</span></span>  
  
 <span data-ttu-id="33c24-268">Voici le schéma XDR équivalent :</span><span class="sxs-lookup"><span data-stu-id="33c24-268">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
  
    <ElementType name="Order" sql:relation="CustOrder" >  
      <AttributeType name="OrderID" />  
      <AttributeType name="CustomerID" />  
      <attribute type="OrderID" />  
      <attribute type="CustomerID" />  
    </ElementType>  
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"   
                       sql:overflow-field="OverflowColumn"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
             <sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
                foreign-relation="CustOrder" />  
      </element>  
   </ElementType>  
</Schema>  
```  
  
## <a name="h-specifying-the-file-path-for-temp-files-in-transaction-mode"></a><span data-ttu-id="33c24-269">H.</span><span class="sxs-lookup"><span data-stu-id="33c24-269">H.</span></span> <span data-ttu-id="33c24-270">Spécification du chemin d'accès aux fichiers temporaires en mode de transaction</span><span class="sxs-lookup"><span data-stu-id="33c24-270">Specifying the file path for temp files in transaction mode</span></span>  
 <span data-ttu-id="33c24-271">Lorsque vous effectuez un chargement en masse en mode de transaction (autrement dit, lorsque la propriété transaction a la valeur TRUE), vous devez également définir la propriété TempFilePath lorsque l’une des conditions suivantes est remplie :</span><span class="sxs-lookup"><span data-stu-id="33c24-271">When you are bulk loading in transaction mode (that is, when the Transaction property is set to TRUE), you also must set the TempFilePath property when either of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="33c24-272">Vous effectuez un chargement en masse sur un serveur distant.</span><span class="sxs-lookup"><span data-stu-id="33c24-272">You are bulk loading to a remote server.</span></span>  
  
-   <span data-ttu-id="33c24-273">Vous souhaitez utiliser un autre dossier ou lecteur local (différent du chemin d'accès spécifié par la variable d'environnement TEMP) pour stocker les fichiers temporaires créés en mode de transaction.</span><span class="sxs-lookup"><span data-stu-id="33c24-273">You want to use an alternate local drive or folder (one other than the path that is specified by the TEMP environment variable) to store the temporary files that are created in the transaction mode.</span></span>  
  
 <span data-ttu-id="33c24-274">Par exemple, le code VBScript suivant effectue un chargement en masse des données à partir du fichier SampleXMLData.xml dans les tables de base de données en mode de transaction.</span><span class="sxs-lookup"><span data-stu-id="33c24-274">For example, the following VBScript code bulk loads data from the SampleXMLData.xml file into the database tables in transaction mode.</span></span> <span data-ttu-id="33c24-275">La propriété TempFilePath est spécifiée pour définir le chemin d’accès pour les fichiers temporaires qui sont générés en mode de transaction.</span><span class="sxs-lookup"><span data-stu-id="33c24-275">The TempFilePath property is specified to set the path for the temporary files that are generated in transaction mode.</span></span>  
  
```  
set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
objBL.CheckConstraints = True  
objBL.Transaction=True  
objBL.TempFilePath="\\Server\MyDir"  
objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
set objBL=Nothing  
```  
  
> [!NOTE]  
>  <span data-ttu-id="33c24-276">Le chemin d'accès aux fichiers temporaires doit être un emplacement partagé accessible au compte de service de l'instance cible de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] et au compte exécutant l'application de chargement en masse.</span><span class="sxs-lookup"><span data-stu-id="33c24-276">The temporary file path must be a shared location that is accessible to the service account of the target instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and to the account that is running the bulk load application.</span></span> <span data-ttu-id="33c24-277">À moins que vous ne procédiez à un chargement en masse sur un serveur local, le chemin d’accès du fichier temporaire doit être un chemin d’accès UNC (par exemple, \\ \nomserveur\nompartage).</span><span class="sxs-lookup"><span data-stu-id="33c24-277">Unless you are bulk loading on a local server, the temporary file path must be a UNC path (such as \\\servername\sharename).</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="33c24-278">Pour tester un exemple fonctionnel</span><span class="sxs-lookup"><span data-stu-id="33c24-278">To test a working sample</span></span>  
  
1.  <span data-ttu-id="33c24-279">Créez cette table dans la base de données **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="33c24-279">Create this table in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust (     CustomerID uniqueidentifier,   
          LastName  varchar(20));  
    GO  
    ```  
  
2.  <span data-ttu-id="33c24-280">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="33c24-280">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="33c24-281">Ajoutez au fichier le schéma XSD suivant :</span><span class="sxs-lookup"><span data-stu-id="33c24-281">Add the following XSD schema to the file:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="ROOT" sql:is-constant="true" >  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element ref="Customers" />  
          </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
  
      <xsd:element name="Customers" sql:relation="Cust" >  
       <xsd:complexType>  
         <xsd:attribute name="CustomerID"  type="xsd:string" />  
         <xsd:attribute name="LastName" type="xsd:string" />  
       </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="33c24-282">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="33c24-282">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="33c24-283">Ajoutez le document XML suivant au fichier :</span><span class="sxs-lookup"><span data-stu-id="33c24-283">Add the following XML document to the file:</span></span>  
  
    ```  
    <ROOT>  
    <Customers CustomerID="6F9619FF-8B86-D011-B42D-00C04FC964FF"   
               LastName="Smith" />  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="33c24-284">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="33c24-284">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="33c24-285">Ajoutez le code VBScript suivant à ce fichier.</span><span class="sxs-lookup"><span data-stu-id="33c24-285">To this file, add the following VBScript code.</span></span> <span data-ttu-id="33c24-286">Modifiez la chaîne de connexion pour fournir le nom de serveur et le nom de base de données appropriés.</span><span class="sxs-lookup"><span data-stu-id="33c24-286">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="33c24-287">Spécifiez le chemin d’accès approprié pour les fichiers qui sont spécifiés en tant que paramètres à la méthode Execute.</span><span class="sxs-lookup"><span data-stu-id="33c24-287">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span> <span data-ttu-id="33c24-288">Spécifiez également le chemin d’accès approprié pour la propriété TempFilePath.</span><span class="sxs-lookup"><span data-stu-id="33c24-288">Also specify the appropriate path for the TempFilePath property.</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Transaction=True  
    objBL.TempFilePath="\\server\folder"  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
5.  <span data-ttu-id="33c24-289">Exécutez le code VBScript.</span><span class="sxs-lookup"><span data-stu-id="33c24-289">Execute the VBScript code.</span></span>  
  
     <span data-ttu-id="33c24-290">Le schéma doit spécifier le correspondant `sql:datatype` pour l’attribut **CustomerID** lorsque la valeur de **CustomerID** est spécifiée en tant que GUID qui comprend des accolades ({et}), par exemple :</span><span class="sxs-lookup"><span data-stu-id="33c24-290">The schema must specify the corresponding `sql:datatype` for the **CustomerID** attribute when the value for **CustomerID** is specified as a GUID that includes braces ({ and }), such as:</span></span>  
  
    ```  
    <ROOT>  
    <Customers CustomerID="{6F9619FF-8B86-D011-B42D-00C04FC964FF}"   
               LastName="Smith" />  
    </ROOT>  
    ```  
  
     <span data-ttu-id="33c24-291">Voici le schéma mis à jour :</span><span class="sxs-lookup"><span data-stu-id="33c24-291">This is the updated schema:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="ROOT" sql:is-constant="true" >  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element ref="Customers" />  
          </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
  
      <xsd:element name="Customers" sql:relation="Cust" >  
       <xsd:complexType>  
         <xsd:attribute name="CustomerID"  type="xsd:string"   
                        sql:datatype="uniqueidentifier" />  
         <xsd:attribute name="LastName" type="xsd:string" />  
       </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
     <span data-ttu-id="33c24-292">Lorsque `sql:datatype` est spécifié en identifiant le type de colonne comme `uniqueidentifier` , l’opération de chargement en masse supprime les accolades ({et}) de la valeur **CustomerID** avant de l’insérer dans la colonne.</span><span class="sxs-lookup"><span data-stu-id="33c24-292">When `sql:datatype` is specified identifying the column type as `uniqueidentifier`, the bulk load operation removes the braces ({ and }) from the **CustomerID** value before inserting it in the column.</span></span>  
  
 <span data-ttu-id="33c24-293">Voici le schéma XDR équivalent :</span><span class="sxs-lookup"><span data-stu-id="33c24-293">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
<ElementType name="ROOT" sql:is-constant="1">  
      <element type="Customers" />  
</ElementType>  
<ElementType name="Customers" sql:relation="Cust" >  
  <AttributeType name="CustomerID"  sql:datatype="uniqueidentifier" />  
  <AttributeType name="LastName"   />  
  
  <attribute type="CustomerID" />  
  <attribute type="LastName"   />  
</ElementType>  
</Schema>  
```  
  
## <a name="i-using-an-existing-database-connection-with-the-connectioncommand-property"></a><span data-ttu-id="33c24-294">I.</span><span class="sxs-lookup"><span data-stu-id="33c24-294">I.</span></span> <span data-ttu-id="33c24-295">Utilisation d'une connexion de base de données existante avec la propriété ConnectionCommand</span><span class="sxs-lookup"><span data-stu-id="33c24-295">Using an existing database connection with the ConnectionCommand property</span></span>  
 <span data-ttu-id="33c24-296">Vous pouvez utiliser une connexion ADO existante pour effectuer un chargement en masse XML.</span><span class="sxs-lookup"><span data-stu-id="33c24-296">You can use an existing ADO connection to bulk load XML.</span></span> <span data-ttu-id="33c24-297">Cela s'avère utile si le chargement en masse XML n'est que l'une des nombreuses opérations à effectuer sur une source de données.</span><span class="sxs-lookup"><span data-stu-id="33c24-297">This is useful if XML Bulk Load is just one of many operations that will be performed on a data source.</span></span>  
  
 <span data-ttu-id="33c24-298">La propriété ConnectionCommand vous permet d’utiliser une connexion ADO existante à l’aide d’un objet de commande ADO.</span><span class="sxs-lookup"><span data-stu-id="33c24-298">The ConnectionCommand property enables you to use an existing ADO connection by using an ADO command object.</span></span> <span data-ttu-id="33c24-299">L'exemple Visual Basic suivant illustre ce concept :</span><span class="sxs-lookup"><span data-stu-id="33c24-299">This is illustrated in the following Visual Basic example:</span></span>  
  
```  
Private Sub Form_Load()  
Dim objBL As New SQLXMLBulkLoad4  
Dim objCmd As New ADODB.Command  
Dim objConn As New ADODB.Connection  
  
'Open a connection to an instance of SQL Server.  
objConn.Open "provider=SQLOLEDB;data source=(local);database=tempdb;integrated security=SSPI"  
'Ask the Command object to use the connection just established.  
Set objCmd.ActiveConnection = objConn  
  
'Tell Bulk Load to use the active command object that is using the Connection obj.  
objBL.ConnectionCommand = objCmd  
objBL.ErrorLogFile = "c:\error.log"  
objBL.CheckConstraints = True  
'The Transaction property must be set to True if you use ConnectionCommand.  
objBL.Transaction = True  
objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
Set objBL = Nothing  
End Sub  
```  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="33c24-300">Pour tester un exemple fonctionnel</span><span class="sxs-lookup"><span data-stu-id="33c24-300">To test a working sample</span></span>  
  
1.  <span data-ttu-id="33c24-301">Créez deux tables dans la base de données **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="33c24-301">Create two tables in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust(  
                   CustomerID   varchar(5) PRIMARY KEY,  
                   CompanyName  varchar(30),  
                   City         varchar(20));  
    GO  
    CREATE TABLE CustOrder(  
                   CustomerID  varchar(5) references Cust (CustomerID),  
                   OrderID     varchar(5) PRIMARY KEY);  
    GO  
    ```  
  
2.  <span data-ttu-id="33c24-302">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="33c24-302">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="33c24-303">Ajoutez au fichier le schéma XSD suivant :</span><span class="sxs-lookup"><span data-stu-id="33c24-303">Add the following XSD schema to the file:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
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
      <xsd:element name="ROOT" sql:is-constant="true" >  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element ref="Customers" />  
          </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
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
              <xsd:attribute name="CustomerID" type="xsd:integer" />  
             </xsd:complexType>  
           </xsd:element>  
         </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="33c24-304">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="33c24-304">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="33c24-305">Ajoutez le document XML suivant au fichier :</span><span class="sxs-lookup"><span data-stu-id="33c24-305">Add the following XML document to the file:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Hanari Carnes</CompanyName>  
        <City>NY</City>  
        <Order OrderID="1" />  
        <Order OrderID="2" />  
      </Customers>  
  
      <Customers>  
        <CustomerID>1112</CustomerID>  
        <CompanyName>Toms Spezialitten</CompanyName>  
         <City>LA</City>  
        <Order OrderID="3" />  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Victuailles en stock</CompanyName>  
        <Order OrderID="4" />  
    </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="33c24-306">Créez une application Visual Basic (Standard EXE) et le code précédent.</span><span class="sxs-lookup"><span data-stu-id="33c24-306">Create a Visual Basic (Standard EXE) application and the preceding code.</span></span> <span data-ttu-id="33c24-307">Ajoutez ces références au projet :</span><span class="sxs-lookup"><span data-stu-id="33c24-307">Add these references to the project:</span></span>  
  
    ```  
    Microsoft XML BulkLoad for SQL Server 4.0 Type Library  
    Microsoft ActiveX Data objects 2.6 Library  
    ```  
  
5.  <span data-ttu-id="33c24-308">Exécutez l'application.</span><span class="sxs-lookup"><span data-stu-id="33c24-308">Execute the application.</span></span>  
  
 <span data-ttu-id="33c24-309">Voici le schéma XDR équivalent :</span><span class="sxs-lookup"><span data-stu-id="33c24-309">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
         <sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
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
  
## <a name="j-bulk-loading-in-xml-data-type-columns"></a><span data-ttu-id="33c24-310">J.</span><span class="sxs-lookup"><span data-stu-id="33c24-310">J.</span></span> <span data-ttu-id="33c24-311">Chargement en masse dans les colonnes de type de données xml</span><span class="sxs-lookup"><span data-stu-id="33c24-311">Bulk loading in xml Data Type columns</span></span>  
 <span data-ttu-id="33c24-312">Si le schéma de mappage spécifie une colonne de [type de données XML](/sql/t-sql/xml/xml-transact-sql) à l’aide de l' `sql:datatype="xml"` annotation, le chargement en masse XML peut copier des éléments enfants XML pour le champ mappé du document source vers cette colonne.</span><span class="sxs-lookup"><span data-stu-id="33c24-312">If the mapping schema specifies a [xml data type](/sql/t-sql/xml/xml-transact-sql) column by using the `sql:datatype="xml"` annotation, XML Bulk Load can copy XML child elements for the mapped field from the source document into this column.</span></span>  
  
 <span data-ttu-id="33c24-313">Examinez le schéma XSD suivant, qui mappe une vue de la table Production.ProductModel dans l'exemple de base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="33c24-313">Consider the following XSD schema, which maps a view of the Production.ProductModel table in the AdventureWorks sample database.</span></span> <span data-ttu-id="33c24-314">Dans ce tableau, le champ CatalogDescription de `xml` type de données est mappé à un **\<Desc>** élément à l’aide des `sql:field` `sql:datatype="xml"` annotations et.</span><span class="sxs-lookup"><span data-stu-id="33c24-314">In this table, the CatalogDescription field of `xml` data type is mapped to a **\<Desc>** element using the `sql:field` and `sql:datatype="xml"` annotations.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
           xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
           xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription">   
  <xsd:element name="ProductModel"  sql:relation="Production.ProductModel" >  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Name" type="xs:string"></xsd:element>  
        <xsd:element name="Desc" sql:field="CatalogDescription" sql:datatype="xml">  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element name="ProductDescription">  
              <xsd:complexType>  
                <xsd:sequence>  
                  <xsd:element name="Summary" type="xs:anyType"/>  
                </xsd:sequence>  
              </xsd:complexType>  
            </xsd:element>  
          </xsd:sequence>  
        </xsd:complexType>  
        </xsd:element>   
     </xsd:sequence>  
     <xsd:attribute name="ProductModelID" sql:field="ProductModelID" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="33c24-315">Pour tester un exemple fonctionnel</span><span class="sxs-lookup"><span data-stu-id="33c24-315">To test a working sample</span></span>  
  
1.  <span data-ttu-id="33c24-316">Assurez-vous que l'exemple de base de données AdventureWorks est installé.</span><span class="sxs-lookup"><span data-stu-id="33c24-316">Verify that the AdventureWorks sample database is installed.</span></span>  
  
2.  <span data-ttu-id="33c24-317">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="33c24-317">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="33c24-318">Copiez le schéma XSD ci-dessus, puis collez-le dans le fichier et enregistrez ce dernier.</span><span class="sxs-lookup"><span data-stu-id="33c24-318">Copy the XSD schema above and paste it into the file and save it.</span></span>  
  
3.  <span data-ttu-id="33c24-319">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom SampleXMLData.xml.</span><span class="sxs-lookup"><span data-stu-id="33c24-319">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="33c24-320">Copiez le document XML ci-dessous et collez-le dans le fichier, puis enregistrez ce dernier dans le même dossier que celui utilisé pour l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="33c24-320">Copy the following XML document below and paste it into the file and save it in the same folder as was used for the previous step.</span></span>  
  
    ```  
    <ProductModel ProductModelID="2005">  
        <Name>Mountain-100 (2005 model)</Name>  
        <Desc><?xml-stylesheet href="ProductDescription.xsl" type="text/xsl"?>  
            <p1:ProductDescription xmlns:p1="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription"   
                  xmlns:wm="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain"   
                  xmlns:wf="http://www.adventure-works.com/schemas/OtherFeatures"   
                  xmlns:html="http://www.w3.org/1999/xhtml"   
                  xmlns="">  
                <p1:Summary>  
                    <html:p>Our top-of-the-line competition mountain bike.   
          Performance-enhancing options include the innovative HL Frame,   
          super-smooth front suspension, and traction for all terrain.  
                            </html:p>  
                </p1:Summary>  
                <p1:Manufacturer>  
                    <p1:Name>AdventureWorks</p1:Name>  
                    <p1:Copyright>2002-2005</p1:Copyright>  
                    <p1:ProductURL>HTTP://www.Adventure-works.com</p1:ProductURL>  
                </p1:Manufacturer>  
                <p1:Features>These are the product highlights.   
                     <wm:Warranty>  
                        <wm:WarrantyPeriod>3 years</wm:WarrantyPeriod>  
                        <wm:Description>parts and labor</wm:Description>  
                    </wm:Warranty><wm:Maintenance>  
                        <wm:NoOfYears>10 years</wm:NoOfYears>  
                        <wm:Description>maintenance contract available through your dealer or any AdventureWorks retail store.</wm:Description>  
                    </wm:Maintenance><wf:wheel>High performance wheels.</wf:wheel><wf:saddle>  
                        <html:i>Anatomic design</html:i> and made from durable leather for a full-day of riding in comfort.</wf:saddle><wf:pedal>  
                        <html:b>Top-of-the-line</html:b> clipless pedals with adjustable tension.</wf:pedal><wf:BikeFrame>Each frame is hand-crafted in our Bothell facility to the optimum diameter   
          and wall-thickness required of a premium mountain frame.   
          The heat-treated welded aluminum frame has a larger diameter tube that absorbs the bumps.</wf:BikeFrame><wf:crankset> Triple crankset; alumunim crank arm; flawless shifting. </wf:crankset></p1:Features>  
                <!-- add one or more of these elements... one for each specific product in this product model -->  
                <p1:Picture>  
                    <p1:Angle>front</p1:Angle>  
                    <p1:Size>small</p1:Size>  
                    <p1:ProductPhotoID>118</p1:ProductPhotoID>  
                </p1:Picture>  
                <!-- add any tags in <specifications> -->  
                <p1:Specifications> These are the product specifications.  
                       <Material>Almuminum Alloy</Material><Color>Available in most colors</Color><ProductLine>Mountain bike</ProductLine><Style>Unisex</Style><RiderExperience>Advanced to Professional riders</RiderExperience></p1:Specifications>  
            </p1:ProductDescription>  
        </Desc>  
    </ProductModel>  
    ```  
  
4.  <span data-ttu-id="33c24-321">Créez un fichier dans votre éditeur de texte ou éditeur XML par défaut, puis enregistrez-le sous le nom BulkloadXml.vbs.</span><span class="sxs-lookup"><span data-stu-id="33c24-321">Create a file in your preferred text or XML editor, and save it as BulkloadXml.vbs.</span></span> <span data-ttu-id="33c24-322">Copiez le code VBScript suivant et collez-le dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="33c24-322">Copy the following VBScript code and paste it into the file.</span></span> <span data-ttu-id="33c24-323">Enregistrez-le dans le même dossier que celui utilisé pour les fichiers de schéma et de données XML.</span><span class="sxs-lookup"><span data-stu-id="33c24-323">Save it in the same folder as was used for the previous XML data and schema files.</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=MyServer;database=AdventureWorks;integrated security=SSPI"  
  
    Dim fso, sAppPath  
    Set fso = CreateObject("Scripting.FileSystemObject")   
    sAppPath = fso.GetFolder(".")   
  
    objBL.ErrorLogFile = sAppPath & "\error.log"  
  
    'Execute XML bulkload using file.  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
5.  <span data-ttu-id="33c24-324">Exécutez le script BulkloadXml.vbs.</span><span class="sxs-lookup"><span data-stu-id="33c24-324">Execute the BulkloadXml.vbs script.</span></span>  
  
  
