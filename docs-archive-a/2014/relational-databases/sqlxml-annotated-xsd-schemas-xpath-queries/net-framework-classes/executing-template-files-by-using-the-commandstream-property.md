---
title: Exécution de fichiers modèles à l’aide de la propriété CommandStream | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- Managed Classes [SQLXML], executing template files
- SQLXML Managed Classes, executing template files
- templates [SQLXML], SQLXML Managed Classes
- CommandStream property
ms.assetid: 55c564e3-56d1-4d85-bcaa-703e2905dd57
author: rothja
ms.author: jroth
ms.openlocfilehash: c57a2ab2f3780a8bc75b53b0cceeee0799fcfcc2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599862"
---
# <a name="executing-template-files-by-using-the-commandstream-property"></a><span data-ttu-id="8328a-102">Exécution de fichiers modèles à l'aide de la propriété CommandStream</span><span class="sxs-lookup"><span data-stu-id="8328a-102">Executing Template Files by Using the CommandStream Property</span></span>
  <span data-ttu-id="8328a-103">Cet exemple montre comment vous pouvez spécifier les fichiers modèles qui se composent de requêtes SQL ou XPath à l’aide de la propriété CommandStream de l’objet SqlXmlCommand.</span><span class="sxs-lookup"><span data-stu-id="8328a-103">This example illustrates how template files that consist of SQL or XPath queries can be specified by using the CommandStream property of the SqlXmlCommand object.</span></span> <span data-ttu-id="8328a-104">Dans cette application, un FileStreamobject est ouvert pour un fichier de commandes, et le flux de fichier est affecté en tant que CommandStream exécuté.</span><span class="sxs-lookup"><span data-stu-id="8328a-104">In this application, a FileStreamobject is opened for a command file, and the file stream is assigned as the CommandStream that is executed.</span></span>  
  
 <span data-ttu-id="8328a-105">Dans l’exemple suivant, la propriété CommandType est spécifiée en tant que SqlXmlCommandType. Template (et non pas en tant que TemplateFile).</span><span class="sxs-lookup"><span data-stu-id="8328a-105">In the following example, the CommandType property is specified as SqlXmlCommandType.Template (not as TemplateFile).</span></span>  
  
 <span data-ttu-id="8328a-106">Il s'agit de l'exemple de modèle XML :</span><span class="sxs-lookup"><span data-stu-id="8328a-106">This is the sample XML template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>  
    SELECT TOP 2 ContactID, FirstName, LastName   
    FROM   Person.Contact  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="8328a-107">Il s'agit de l'exemple d'application C#.</span><span class="sxs-lookup"><span data-stu-id="8328a-107">This is the sample C# application.</span></span> <span data-ttu-id="8328a-108">Pour tester l'application, enregistrez le modèle (TemplateFile.xml),  puis exécutez l'application.</span><span class="sxs-lookup"><span data-stu-id="8328a-108">To test the application, save the template (TemplateFile.xml) and then execute the application.</span></span> <span data-ttu-id="8328a-109">L'application exécute la requête spécifiée dans le modèle XML et affiche le document XML généré sur l'écran.</span><span class="sxs-lookup"><span data-stu-id="8328a-109">The application executes the query that is specified in the XML template and displays the XML document that is generated on the screen.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8328a-110">Dans le code, vous devez fournir le nom de l'instance de Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="8328a-110">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
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
         MemoryStream ms = new MemoryStream();  
         StreamWriter sw = new StreamWriter(ms);  
         ms.Position = 0;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandStream = new FileStream("TemplateFile.xml", FileMode.Open, FileAccess.Read);  
         cmd.CommandType = SqlXmlCommandType.Template;  
         using (Stream strm = cmd.ExecuteStream())  
         {  
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
  
### <a name="to-test-the-application"></a><span data-ttu-id="8328a-111">Pour tester l'application</span><span class="sxs-lookup"><span data-stu-id="8328a-111">To test the application</span></span>  
  
1.  <span data-ttu-id="8328a-112">Enregistrez le modèle XML (TemplateFile.xml) fourni dans cet exemple dans un dossier.</span><span class="sxs-lookup"><span data-stu-id="8328a-112">Save the XML template (TemplateFile.xml) that is provided in this example in a folder.</span></span>  
  
2.  <span data-ttu-id="8328a-113">Enregistrez le code C# (DocSample.cs) fourni dans cet exemple dans le même dossier que celui dans lequel le schéma est stocké.</span><span class="sxs-lookup"><span data-stu-id="8328a-113">Save the C# code (DocSample.cs) that is provided in this example in the same folder in which the schema is stored.</span></span> <span data-ttu-id="8328a-114">(Si vous stockez les fichiers dans un dossier différent, vous devrez modifier le code et spécifier le chemin d'accès approprié au répertoire pour le schéma de mappage.)</span><span class="sxs-lookup"><span data-stu-id="8328a-114">(If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.)</span></span>  
  
3.  <span data-ttu-id="8328a-115">Compilez le code.</span><span class="sxs-lookup"><span data-stu-id="8328a-115">Compile the code.</span></span> <span data-ttu-id="8328a-116">Pour compiler le code à l'invite de commandes, utilisez :</span><span class="sxs-lookup"><span data-stu-id="8328a-116">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="8328a-117">Un fichier exécutable (DocSample.exe) est alors créé.</span><span class="sxs-lookup"><span data-stu-id="8328a-117">This creates an executable (DocSample.exe).</span></span>  
  
4.  <span data-ttu-id="8328a-118">À l'invite de commandes, exécutez DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="8328a-118">At the command prompt, execute DocSample.exe.</span></span>  
  
  
