---
title: Exécution de requêtes XPath (fournisseur SQLXMLOLEDB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXMLOLEDB Provider, executing XPath queries
- queries [SQLXML], SQLXMLOLEDB Provider
- Base Path property
- XPath queries [SQLXML], SQLXMLOLEDB Provider
- Mapping Schema property
ms.assetid: 19063222-dc9c-48ae-a55f-778103674a9e
author: rothja
ms.author: jroth
ms.openlocfilehash: 667bc8dfd95c37c0a10c0bc68f3007e7d04533e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700908"
---
# <a name="executing-xpath-queries-sqlxmloledb-provider"></a><span data-ttu-id="d054b-102">Exécution de requêtes XPath (fournisseur SQLXMLOLEDB)</span><span class="sxs-lookup"><span data-stu-id="d054b-102">Executing XPath Queries (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="d054b-103">Cet exemple illustre l'utilisation des propriétés suivantes spécifiques au fournisseur SQLXMLOLEDB :</span><span class="sxs-lookup"><span data-stu-id="d054b-103">This example illustrates the use of the following SQLXMLOLEDB Provider-specific properties:</span></span>  
  
-   `ClientSideXML`  
  
-   `Base Path`  
  
-   `Mapping Schema`  
  
 <span data-ttu-id="d054b-104">Dans cet exemple d'application ADO, une requête XPath (root) est spécifiée contre un schéma de mappage XSD (MySchema.xml).</span><span class="sxs-lookup"><span data-stu-id="d054b-104">In this sample ADO application, an XPath query (root) is specified against an XSD mapping schema (MySchema.xml).</span></span> <span data-ttu-id="d054b-105">Le schéma a un **\<Contacts>** élément avec les attributs **ContactID**, **FirstName**et **LastName** .</span><span class="sxs-lookup"><span data-stu-id="d054b-105">The schema has a **\<Contacts>** element with **ContactID**, **FirstName**, and **LastName** attributes.</span></span> <span data-ttu-id="d054b-106">Dans le schéma, le mappage par défaut a lieu : un nom d'élément mappe à la table avec le même nom et les attributs de type simple mappent aux colonnes avec les mêmes noms.</span><span class="sxs-lookup"><span data-stu-id="d054b-106">In the schema, default mapping takes place: an element name maps to the table with the same name, and attributes of simple type map to the columns with the same names.</span></span>  
  
```  
<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'  
   xmlns:sql='urn:schemas-microsoft-com:mapping-schema'>  
 <xsd:element name= 'root' sql:is-constant='1'>   
    <xsd:complexType>  
       <xsd:sequence>  
         <xsd:element ref = 'Contacts'/>  
       </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
  <xsd:element name='Contacts' sql:relation='Person.Contact'>   
     <xsd:complexType>  
          <xsd:attribute name='ContactID' type='xsd:integer' />  
          <xsd:attribute name='FirstName' type='xsd:string'/>   
          <xsd:attribute name='LastName' type='xsd:string' />   
     </xsd:complexType>  
   </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="d054b-107">La propriété schéma de mappage fournit le schéma de mappage par rapport auquel la requête XPath est exécutée.</span><span class="sxs-lookup"><span data-stu-id="d054b-107">The Mapping Schema property provides the mapping schema against which the XPath query is executed.</span></span> <span data-ttu-id="d054b-108">Le schéma de mappage peut être un schéma XSD ou XDR.</span><span class="sxs-lookup"><span data-stu-id="d054b-108">The mapping schema can be an XSD or XDR schema.</span></span> <span data-ttu-id="d054b-109">La propriété chemin d’accès de base fournit le chemin d’accès du fichier au schéma de mappage.</span><span class="sxs-lookup"><span data-stu-id="d054b-109">The Base Path property provides the file path to the mapping schema.</span></span>  
  
 <span data-ttu-id="d054b-110">La propriété ClientSideXML a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="d054b-110">The ClientSideXML property is set to True.</span></span> <span data-ttu-id="d054b-111">Par conséquent, le document XML est généré sur le client.</span><span class="sxs-lookup"><span data-stu-id="d054b-111">Therefore, the XML document is generated on the client.</span></span>  
  
 <span data-ttu-id="d054b-112">Dans l'application, une requête XPath est spécifiée directement.</span><span class="sxs-lookup"><span data-stu-id="d054b-112">In the application, an XPath query is specified directly.</span></span> <span data-ttu-id="d054b-113">Par conséquent, le dialecte XPath {ec2a4293-e898-11d2-b1b7-00c04f680c56} doit être inclus.</span><span class="sxs-lookup"><span data-stu-id="d054b-113">Therefore, the XPath dialect {ec2a4293-e898-11d2-b1b7-00c04f680c56} must be included.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d054b-114">Dans le code, vous devez fournir le nom de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="d054b-114">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="d054b-115">En outre, cet exemple spécifie l’utilisation de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) pour le fournisseur de données qui requiert l’installation d’un logiciel client réseau supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="d054b-115">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) for the data provider which requires additional network client software to be installed.</span></span> <span data-ttu-id="d054b-116">Pour plus d’informations, consultez [Configuration système requise pour SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="d054b-116">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Sub main()  
Dim oTestStream As New ADODB.Stream  
Dim oTestConnection As New ADODB.Connection  
Dim oTestCommand As New ADODB.Command  
  
oTestConnection.Open "provider=SQLXMLOLEDB.4.0;data provider=SQLNCLI11;data source=SqlServerName;initial catalog=AdventureWorks;Integrated Security= SSPI;"  
  
oTestCommand.ActiveConnection = oTestConnection  
oTestCommand.Properties("ClientSideXML") = True  
  
oTestCommand.CommandText = "root"  
oTestStream.Open  
oTestCommand.Dialect = "{ec2a4293-e898-11d2-b1b7-00c04f680c56}"  
oTestCommand.Properties("Output Stream").Value = oTestStream  
oTestCommand.Properties("Base Path").Value = "c:\Schemas\SQLXML4\XPathDirect\"  
oTestCommand.Properties("Mapping Schema").Value = "mySchema.xml"  
oTestCommand.Properties("Output Encoding") = "utf-8"  
oTestCommand.Execute , , adExecuteStream  
oTestStream.Position = 0  
oTestStream.Charset = "utf-8"  
Debug.Print oTestStream.ReadText(adReadAll)  
  
End Sub  
Sub Form_Load()  
 main  
End Sub  
```  
  
  
