---
title: Exécution de requêtes XPath avec des espaces de noms (classes managées SQLXML) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- namespaces property
- XPath queries [SQLXML], SQLXML Managed Classes
- queries [SQLXML], SQLXML Managed Classes
- XPath queries [SQLXML], namespaces
- Managed Classes [SQLXML], executing XPath queries
- SQLXML Managed Classes, executing XPath queries
- namespaces [SQLXML], XPath queries
ms.assetid: c6fc46d8-6b42-4992-a8f1-a8d4b8886e6e
author: rothja
ms.author: jroth
ms.openlocfilehash: a2d726de95929709c1ae958ee22388df3195bc84
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599859"
---
# <a name="executing-xpath-queries-with-namespaces-sqlxml-managed-classes"></a><span data-ttu-id="535fc-102">Exécution de requêtes XPath avec des espaces de noms (classes managées SQLXML)</span><span class="sxs-lookup"><span data-stu-id="535fc-102">Executing XPath Queries with Namespaces (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="535fc-103">Les requêtes XPath peuvent inclure des espaces de noms.</span><span class="sxs-lookup"><span data-stu-id="535fc-103">XPath queries can include namespaces.</span></span> <span data-ttu-id="535fc-104">Si les éléments de schéma sont qualifiés par un espace de noms (utilisent un espace de noms cible), les requêtes XPath sur le schéma doivent spécifier cet espace de noms.</span><span class="sxs-lookup"><span data-stu-id="535fc-104">If the schema elements are namespace-qualified (use a target namespace), the XPath queries against the schema must specify the namespace.</span></span>  
  
 <span data-ttu-id="535fc-105">Le caractère générique (\*) n'étant pas prise en charge dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, vous devez spécifier la requête XPath en utilisant un préfixe d'espace de noms.</span><span class="sxs-lookup"><span data-stu-id="535fc-105">Because the wildcard character (\*) is not supported in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, you must specify the XPath query by using a namespace prefix.</span></span> <span data-ttu-id="535fc-106">Pour résoudre le préfixe, utilisez la propriété Namespaces pour spécifier la liaison d’espace de noms.</span><span class="sxs-lookup"><span data-stu-id="535fc-106">To resolve the prefix, use the namespaces property to specify the namespace binding.</span></span>  
  
 <span data-ttu-id="535fc-107">Dans l’exemple suivant, la requête XPath spécifie des espaces de noms à l’aide du caractère générique ( \* ) et des fonctions XPath local name () et namespace-URI ().</span><span class="sxs-lookup"><span data-stu-id="535fc-107">In the following example, the XPath query specifies namespaces by using the wildcard character (\*) and the local-name() and namespace-uri() XPath functions.</span></span> <span data-ttu-id="535fc-108">Cette requête XPath retourne tous les éléments pour lesquels le nom local est `Employee` et l'URI d'espace de noms est `urn:myschema:Contacts` :</span><span class="sxs-lookup"><span data-stu-id="535fc-108">This XPath query returns all the elements where the local name is `Employee` and the namespace URI is `urn:myschema:Contacts`:</span></span>  
  
```  
/*[local-name() = 'Contact' and namespace-uri() = 'urn:myschema:Contacts']  
```  
  
 <span data-ttu-id="535fc-109">Dans SQLXML 4.0, spécifiez cette requête XPath avec un préfixe d'espace de noms.</span><span class="sxs-lookup"><span data-stu-id="535fc-109">In SQLXML 4.0, specify this XPath query with a namespace prefix.</span></span> <span data-ttu-id="535fc-110">`x:Contact` constitue un exemple, où `x` est le préfixe d'espace de noms.</span><span class="sxs-lookup"><span data-stu-id="535fc-110">An example is `x:Contact`, where `x` is the namespace prefix.</span></span> <span data-ttu-id="535fc-111">Prenons le schéma XSD suivant :</span><span class="sxs-lookup"><span data-stu-id="535fc-111">Consider the following XSD schema:</span></span>  
  
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
  
 <span data-ttu-id="535fc-112">Comme ce schéma définit l'espace de noms cible, une requête Xpath (telle que « Employee ») sur ce schéma doit inclure l'espace de noms.</span><span class="sxs-lookup"><span data-stu-id="535fc-112">Because this schema defines the target namespace, an XPath query (such as "Employee") against this schema must include the namespace.</span></span>  
  
 <span data-ttu-id="535fc-113">L'exemple d'application C# suivant exécute une requête XPath sur le schéma XSD précédent (MySchema.xml).</span><span class="sxs-lookup"><span data-stu-id="535fc-113">The following C# sample application executes an XPath query against the preceding XSD schema (MySchema.xml).</span></span> <span data-ttu-id="535fc-114">Pour résoudre le préfixe, spécifiez la liaison d’espace de noms à l’aide de la propriété namespaces de l’objet SqlXmlCommand.</span><span class="sxs-lookup"><span data-stu-id="535fc-114">To resolve the prefix, specify the namespace binding by using the Namespaces property of the SqlXmlCommand object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="535fc-115">Dans le code, vous devez fournir le nom de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="535fc-115">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
      public static int testXPath()  
      {  
         //Stream strm;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandText = "x:Contact[@CID='1']";  
         cmd.CommandType = SqlXmlCommandType.XPath;  
         cmd.RootTag = "ROOT";  
         cmd.Namespaces = "xmlns:x='urn:myschema:Contacts'";  
         cmd.SchemaPath = "MySchema.xml";  
         using (Stream strm = cmd.ExecuteStream()){  
            using (StreamReader sr = new StreamReader(strm)){  
               Console.WriteLine(sr.ReadToEnd());  
            }  
         }  
         return 0;  
      }  
      public static int Main(String[] args)  
      {  
         testXPath();  
         return 0;  
      }  
   }  
```  
  
 <span data-ttu-id="535fc-116">Pour tester cet exemple, le [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework doit être installé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="535fc-116">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="535fc-117">Pour tester l'application</span><span class="sxs-lookup"><span data-stu-id="535fc-117">To test the application</span></span>  
  
1.  <span data-ttu-id="535fc-118">Enregistrez dans un dossier le schéma XSD (MySchema.xml) fourni dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="535fc-118">Save the XSD schema (MySchema.xml) that is provided in this example in a folder.</span></span>  
  
2.  <span data-ttu-id="535fc-119">Enregistrez le code C# (DocSample.cs) fourni dans cet exemple dans le même dossier que celui dans lequel le schéma est stocké.</span><span class="sxs-lookup"><span data-stu-id="535fc-119">Save the C# code (DocSample.cs) that is provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="535fc-120">(Si vous stockez les fichiers dans un dossier différent, vous devrez modifier le code et spécifier le chemin d'accès approprié au répertoire pour le schéma de mappage.)</span><span class="sxs-lookup"><span data-stu-id="535fc-120">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
3.  <span data-ttu-id="535fc-121">Compilez le code.</span><span class="sxs-lookup"><span data-stu-id="535fc-121">Compile the code.</span></span> <span data-ttu-id="535fc-122">Pour compiler le code à l'invite de commandes, utilisez :</span><span class="sxs-lookup"><span data-stu-id="535fc-122">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="535fc-123">Un fichier exécutable (DocSample.exe) est alors créé.</span><span class="sxs-lookup"><span data-stu-id="535fc-123">This creates an executable (DocSample.exe).</span></span>  
  
4.  <span data-ttu-id="535fc-124">À l'invite de commandes, exécutez DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="535fc-124">At the command prompt, execute DocSample.exe.</span></span>  
  
  
