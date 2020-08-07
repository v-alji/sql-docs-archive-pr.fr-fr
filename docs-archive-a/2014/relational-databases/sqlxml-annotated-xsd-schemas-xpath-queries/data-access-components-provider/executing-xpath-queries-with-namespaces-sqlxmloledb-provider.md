---
title: Exécution de requêtes XPath avec des espaces de noms (fournisseur SQLXMLOLEDB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXMLOLEDB Provider, executing XPath queries
- namespaces property
- queries [SQLXML], SQLXMLOLEDB Provider
- XPath queries [SQLXML], namespaces
- XPath queries [SQLXML], SQLXMLOLEDB Provider
- namespaces [SQLXML], XPath queries
ms.assetid: 024a4b7d-435d-47ba-9e80-2c2f640108f5
author: rothja
ms.author: jroth
ms.openlocfilehash: ff692b49a4c32c14655af3a9eb07071dc60ba2a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700895"
---
# <a name="executing-xpath-queries-with-namespaces-sqlxmloledb-provider"></a><span data-ttu-id="59110-102">Exécution de requêtes XPath avec des espaces de noms (fournisseur SQLXMLOLEDB)</span><span class="sxs-lookup"><span data-stu-id="59110-102">Executing XPath Queries with Namespaces (SQLXMLOLEDB Provider)</span></span>
  <span data-ttu-id="59110-103">Les requêtes XPath peuvent inclure des espaces de noms.</span><span class="sxs-lookup"><span data-stu-id="59110-103">XPath queries can include namespaces.</span></span> <span data-ttu-id="59110-104">Si les éléments de schéma sont qualifiés par un espace de noms (autrement dit, s'ils incluent un espace de noms cible), les requêtes XPath contre le schéma doivent spécifier cet espace de noms.</span><span class="sxs-lookup"><span data-stu-id="59110-104">If the schema elements are namespace qualified (that is, if they include a target namespace), XPath queries against the schema must specify this namespace.</span></span>  
  
 <span data-ttu-id="59110-105">L'utilisation du caractère générique (\*) n'étant pas prise en charge dans SQLXML 4.0, vous devez spécifier la requête XPath en utilisant un préfixe d'espace de noms.</span><span class="sxs-lookup"><span data-stu-id="59110-105">Because using the wildcard character (\*) is not supported in SQLXML 4.0, you must specify the XPath query by using a namespace prefix.</span></span> <span data-ttu-id="59110-106">Pour résoudre ce préfixe, utilisez la propriété Namespaces pour spécifier la liaison d’espace de noms.</span><span class="sxs-lookup"><span data-stu-id="59110-106">To resolve this prefix, use the namespaces property to specify the namespace binding.</span></span>  
  
 <span data-ttu-id="59110-107">Dans l’exemple suivant, la requête XPath spécifie des espaces de noms à l’aide du caractère générique ( \* ) et des fonctions XPath local name () et namespace-URI ().</span><span class="sxs-lookup"><span data-stu-id="59110-107">In the following example, the XPath query specifies namespaces by using the wildcard character (\*) and the local-name() and namespace-uri() XPath functions.</span></span> <span data-ttu-id="59110-108">Cette requête XPath retourne tous les éléments dont le nom local est `Contact` et l'URI d'espace de noms est `urn:myschema:Contacts`.</span><span class="sxs-lookup"><span data-stu-id="59110-108">This XPath query returns all the elements where the local name is `Contact` and the namespace URI is `urn:myschema:Contacts`.</span></span>  
  
```  
/*[local-name() = 'Contact' and namespace-uri() = 'urn:myschema:Contacts']  
```  
  
 <span data-ttu-id="59110-109">Dans SQLXML 4.0, cette requête XPath doit être spécifiée avec un préfixe d'espace de noms.</span><span class="sxs-lookup"><span data-stu-id="59110-109">In SQLXML 4.0, this XPath query must be specified with a namespace prefix.</span></span> <span data-ttu-id="59110-110">`x:Contact` constitue un exemple, où `x` est le préfixe d'espace de noms.</span><span class="sxs-lookup"><span data-stu-id="59110-110">An example is `x:Contact`, where `x` is the namespace prefix.</span></span> <span data-ttu-id="59110-111">Prenons le schéma XSD suivant :</span><span class="sxs-lookup"><span data-stu-id="59110-111">Consider the following XSD schema:</span></span>  
  
```  
<schema xmlns="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
            xmlns:con="urn:myschema:Contacts"  
            targetNamespace="urn:myschema:Contacts">  
<complexType name="ContactType">  
  <attribute name="CID" sql:field="ContactID" type="ID"/>  
  <attribute name="FName" sql:field="FirstName" type="string"/>  
  <attribute name="LName" sql:field="LastName"/>   
</complexType>  
<element name="Contact" type="con:ContactType" sql:relation="Person.Contact"/>  
</schema>  
```  
  
 <span data-ttu-id="59110-112">Étant donné que ce schéma définit l'espace de noms cible, une requête Xpath (telle que « Employee ») contre le schéma doit inclure l'espace de noms.</span><span class="sxs-lookup"><span data-stu-id="59110-112">Because this schema defines the target namespace, an XPath query (such as "Employee") against the schema must include the namespace.</span></span>  
  
 <span data-ttu-id="59110-113">Voici un exemple d'application [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic qui exécute une requête XPath (x:Employee) contre le schéma XSD précédent.</span><span class="sxs-lookup"><span data-stu-id="59110-113">This is a sample [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic application that executes an XPath query (x:Employee) against the preceding XSD schema.</span></span> <span data-ttu-id="59110-114">Pour résoudre le préfixe, la liaison d’espace de noms est spécifiée à l’aide de la propriété Namespaces.</span><span class="sxs-lookup"><span data-stu-id="59110-114">To resolve the prefix, the namespace binding is specified by using the namespaces property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59110-115">Dans le code, vous devez fournir le nom de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="59110-115">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span> <span data-ttu-id="59110-116">En outre, cet exemple spécifie l'utilisation de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) comme fournisseur de données, ce qui requiert l'installation d'un logiciel client réseau supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="59110-116">Also, this example specifies the use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) for the data provider, which requires additional network client software to be installed.</span></span> <span data-ttu-id="59110-117">Pour plus d’informations, consultez [Configuration système requise pour SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="59110-117">For more information, see [System Requirements for SQL Server Native Client](../../native-client/system-requirements-for-sql-server-native-client.md).</span></span>  
  
```  
Option Explicit  
Private Sub Form_Load()  
    Dim con As New ADODB.Connection  
    Dim cmd As New ADODB.Command  
    Dim stm As New ADODB.Stream  
    con.Open "provider=SQLXMLOLEDB.4.0;Data Provider=SQLNCLI11;Data Source=SqlServerName;Initial Catalog=AdventureWorks;Integrated Security=SSPI;"  
    Set cmd.ActiveConnection = con  
    stm.Open  
    cmd.Properties("Output Stream").Value = stm  
    cmd.Properties("Output Encoding") = "utf-8"  
    cmd.Properties("Mapping schema") = "C:\DirectoryPath\con-ex.xml"  
    cmd.Properties("namespaces") = "xmlns:x='urn:myschema:Contacts'"  
    '  Debug.Print "Set Command Dialect to DBGUID_XPATH"  
    cmd.Dialect = "{ec2a4293-e898-11d2-b1b7-00c04f680c56}"  
    cmd.CommandText = "x:Contact"  
    cmd.Execute , , adExecuteStream   
    stm.Position = 0  
    Debug.Print stm.ReadText(adReadAll)  
End Sub  
```  
  
### <a name="to-test-this-application"></a><span data-ttu-id="59110-118">Pour tester cette application</span><span class="sxs-lookup"><span data-stu-id="59110-118">To test this application</span></span>  
  
1.  <span data-ttu-id="59110-119">Enregistrez l'exemple de schéma XSD dans un dossier.</span><span class="sxs-lookup"><span data-stu-id="59110-119">Save the sample XSD schema in a folder.</span></span>  
  
2.  <span data-ttu-id="59110-120">Créez un projet exécutable Visual Basic et copiez-y le code.</span><span class="sxs-lookup"><span data-stu-id="59110-120">Create a Visual Basic executable project, and copy the code into it.</span></span> <span data-ttu-id="59110-121">Modifiez le chemin d'accès au répertoire spécifié comme il se doit.</span><span class="sxs-lookup"><span data-stu-id="59110-121">Change the specified directory path as appropriate.</span></span>  
  
3.  <span data-ttu-id="59110-122">Ajoutez la référence de projet suivante :</span><span class="sxs-lookup"><span data-stu-id="59110-122">Add the following project reference:</span></span>  
  
    ```  
    "Microsoft ActiveX Data Objects 2.8 Library"  
    ```  
  
4.  <span data-ttu-id="59110-123">Exécutez l'application.</span><span class="sxs-lookup"><span data-stu-id="59110-123">Execute the application.</span></span>  
  
 <span data-ttu-id="59110-124">Voici le résultat partiel :</span><span class="sxs-lookup"><span data-stu-id="59110-124">This is the partial result:</span></span>  
  
```  
<y0:Employee xmlns:y0="urn:myschema:Contacts"   
             LName="Achong" CID="1" FName="Gustavo"/>  
<y0:Employee xmlns:y0="urn:myschema:Employees"   
             LName="Abel" CID="2" FName="Catherine"/>  
```  
  
 <span data-ttu-id="59110-125">Les préfixes générés dans le document XML sont arbitraires, mais ils mappent au même espace de noms.</span><span class="sxs-lookup"><span data-stu-id="59110-125">The prefixes that are generated in the XML document are arbitrary, but they map to the same namespace.</span></span>  
  
  
