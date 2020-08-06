---
title: Exécution de fichiers modèles à l’aide de la propriété CommandText | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- Managed Classes [SQLXML], executing template files
- SQLXML Managed Classes, executing template files
- templates [SQLXML], SQLXML Managed Classes
- executing template files [SQLXML]
- CommandText property
ms.assetid: f1b1278d-252d-4a06-836e-4ef77f338ef9
author: rothja
ms.author: jroth
ms.openlocfilehash: f5507e84daf57ca4646fae3efe78c6105af35700
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599861"
---
# <a name="executing-template-files-by-using-the-commandtext-property"></a><span data-ttu-id="27e66-102">Exécution de fichiers modèles à l'aide de la propriété CommandText</span><span class="sxs-lookup"><span data-stu-id="27e66-102">Executing Template Files by Using the CommandText Property</span></span>
  <span data-ttu-id="27e66-103">Cet exemple illustre la façon dont les fichiers de modèle qui se composent de requêtes SQL ou XPath peuvent être spécifiés à l’aide de CommandTextproperty.</span><span class="sxs-lookup"><span data-stu-id="27e66-103">This example illustrates how template files that consist of SQL or XPath queries can be specified by using the CommandTextproperty.</span></span> <span data-ttu-id="27e66-104">Au lieu de spécifier la requête SQL ou XPath comme valeur de CommandText, vous pouvez spécifier un nom de fichier comme valeur.</span><span class="sxs-lookup"><span data-stu-id="27e66-104">Instead of specifying the SQL or XPath query as the value of CommandText, you can specify a file name as the value.</span></span> <span data-ttu-id="27e66-105">Dans l’exemple suivant, la propriété CommandType est spécifiée en tant que SqlXmlCommandType. TemplateFile.</span><span class="sxs-lookup"><span data-stu-id="27e66-105">In the following example, the CommandType property is specified as SqlXmlCommandType.TemplateFile.</span></span>  
  
 <span data-ttu-id="27e66-106">L'exemple d'application exécute ce modèle :</span><span class="sxs-lookup"><span data-stu-id="27e66-106">The sample application executes this template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>  
    SELECT TOP 2 ContactID, FirstName, LastName   
    FROM   Person.Contact  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="27e66-107">Il s’agit de l’exemple d’application C#.</span><span class="sxs-lookup"><span data-stu-id="27e66-107">This is the C# sample application.</span></span> <span data-ttu-id="27e66-108">Pour tester l'application, enregistrez le modèle (TemplateFile.xml),  puis exécutez l'application.</span><span class="sxs-lookup"><span data-stu-id="27e66-108">To test the application, save the template (TemplateFile.xml) and then execute the application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="27e66-109">Dans le code, vous devez fournir le nom de l'instance de Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="27e66-109">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
  
      public static int testParams()  
      {  
         //Stream strm;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandType = SqlXmlCommandType.TemplateFile;  
         cmd.CommandText = "TemplateFile.xml";  
         using (Stream strm = cmd.ExecuteStream()){  
            using (StreamReader sr = new StreamReader(strm)){  
                Console.WriteLine(sr.ReadToEnd());  
            }  
         }  
  
         return 0;        
      }  
      public static int Main(String[] args)  
      {  
         testParams();     
         return 0;  
      }  
   }  
```  
  
### <a name="to-test-the-application"></a><span data-ttu-id="27e66-110">Pour tester l'application</span><span class="sxs-lookup"><span data-stu-id="27e66-110">To test the application</span></span>  
  
1.  <span data-ttu-id="27e66-111">Assurez-vous que le [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework est installé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="27e66-111">Make sure that you have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
2.  <span data-ttu-id="27e66-112">Enregistrez le modèle XML (TemplateFile.xml) fourni dans cet exemple dans un dossier.</span><span class="sxs-lookup"><span data-stu-id="27e66-112">Save the XML template (TemplateFile.xml) that is provided in this example in a folder.</span></span>  
  
3.  <span data-ttu-id="27e66-113">Enregistrez le code C# (DocSample.cs) fourni dans cet exemple dans le même dossier que celui dans lequel le schéma est stocké.</span><span class="sxs-lookup"><span data-stu-id="27e66-113">Save the C# code (DocSample.cs) that is provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="27e66-114">(Si vous stockez les fichiers dans un dossier différent, vous devrez modifier le code et spécifier le chemin d'accès approprié au répertoire pour le schéma de mappage.)</span><span class="sxs-lookup"><span data-stu-id="27e66-114">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
4.  <span data-ttu-id="27e66-115">Compilez le code.</span><span class="sxs-lookup"><span data-stu-id="27e66-115">Compile the code.</span></span> <span data-ttu-id="27e66-116">Pour compiler le code à l'invite de commandes, utilisez :</span><span class="sxs-lookup"><span data-stu-id="27e66-116">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="27e66-117">Un fichier exécutable (DocSample.exe) est alors créé.</span><span class="sxs-lookup"><span data-stu-id="27e66-117">This creates an executable (DocSample.exe).</span></span>  
  
5.  <span data-ttu-id="27e66-118">À l'invite de commandes, exécutez DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="27e66-118">At the command prompt, execute DocSample.exe.</span></span>  
  
 <span data-ttu-id="27e66-119">Si vous transmettez un paramètre à un modèle, le nom du paramètre doit commencer par arobase (@); par exemple, p.Name = " @ContactID ", où p est un objet SqlXmlParameter.</span><span class="sxs-lookup"><span data-stu-id="27e66-119">If you pass a parameter to a template, the parameter name must begin with at sign (@); for example, p.Name="@ContactID", where p is a SqlXmlParameter object.</span></span>  
  
 <span data-ttu-id="27e66-120">Voici le modèle mis à jour qui prend un paramètre.</span><span class="sxs-lookup"><span data-stu-id="27e66-120">This is the updated template which takes one parameter.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:header>  
     <sql:param name='ContactID'>1</sql:param>    
  </sql:header>  
  <sql:query>  
    SELECT ContactID, FirstName, LastName  
    FROM   Person.Contact  
    WHERE  ContactID=@ContactID  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="27e66-121">Voici le code mis à jour dans lequel un paramètre est passé pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="27e66-121">This is the updated code in which a parameter is passed in to execute the template.</span></span>  
  
```  
public static int testParams()  
{  
  
   Stream strm;  
   SqlXmlParameter p;  
  
   SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
   cmd.CommandType = SqlXmlCommandType.TemplateFile;  
   cmd.CommandText = "TemplateFile.xml";  
   p = cmd.CreateParameter();  
   p.Name="@ContactID";  
   p.Value = "1";  
   strm = cmd.ExecuteStream();  
   StreamReader sw = new StreamReader(strm);  
   Console.WriteLine(sw.ReadToEnd());  
   return 0;        
}  
```  
  
  
