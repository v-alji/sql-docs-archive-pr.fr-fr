---
title: Exécution de requêtes SQL (classes managées SQLXML) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- queries [SQLXML], SQLXML Managed Classes
- SQLXML Managed Classes, executing SQL queries
- Managed Classes [SQLXML], executing SQL queries
- ExecuteToStream method
- SQL queries [SQLXML]
ms.assetid: a561ae83-a8b6-4b9b-a819-9b86839546b4
author: rothja
ms.author: jroth
ms.openlocfilehash: d869e45de359e602b2451b9f66fa3046f6823c1e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610526"
---
# <a name="executing-sql-queries-sqlxml-managed-classes"></a><span data-ttu-id="af226-102">Exécution de requêtes SQL (classes managées SQLXML)</span><span class="sxs-lookup"><span data-stu-id="af226-102">Executing SQL Queries (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="af226-103">Cet exemple illustre les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="af226-103">This example demonstrates:</span></span>  
  
-   <span data-ttu-id="af226-104">Création de paramètres (objets SqlXmlParameter).</span><span class="sxs-lookup"><span data-stu-id="af226-104">Creating parameters (SqlXmlParameter objects).</span></span>  
  
-   <span data-ttu-id="af226-105">Affectation de valeurs aux propriétés (nom et valeur) des objets SqlXmlParameter.</span><span class="sxs-lookup"><span data-stu-id="af226-105">Assigning values to the properties (Name and Value) of SqlXmlParameter objects.</span></span>  
  
 <span data-ttu-id="af226-106">Dans cet exemple, une simple requête SQL est exécutée dans le but d'extraire le prénom, le nom et la date de naissance de l'employé dont la valeur désignant le nom est passée en tant que paramètre.</span><span class="sxs-lookup"><span data-stu-id="af226-106">In this example, a simple SQL query is executed to retrieve the first name, last name, and birth date of the employee whose last name value is passed as a parameter.</span></span> <span data-ttu-id="af226-107">En spécifiant le paramètre (*LastName*), seule la propriété Value est définie.</span><span class="sxs-lookup"><span data-stu-id="af226-107">In specifying the parameter (*LastName*), only the Value property is set.</span></span> <span data-ttu-id="af226-108">La propriété Name n’est pas définie, car dans cette requête, le paramètre est positionnel et aucun nom n’est requis.</span><span class="sxs-lookup"><span data-stu-id="af226-108">The Name property is not set, because in this query the parameter is positional and no name is required.</span></span>  
  
 <span data-ttu-id="af226-109">La propriété CommandType de l’objet SqlXmlCommand par défaut est **SQL**.</span><span class="sxs-lookup"><span data-stu-id="af226-109">The CommandType property of the SqlXmlCommand object by default is **Sql**.</span></span> <span data-ttu-id="af226-110">Par conséquent, la propriété n'est pas explicitement définie.</span><span class="sxs-lookup"><span data-stu-id="af226-110">Therefore, the property is not explicitly set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="af226-111">Dans le code, vous devez fournir le nom de l'instance de Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="af226-111">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
 <span data-ttu-id="af226-112">Voici le code C# :</span><span class="sxs-lookup"><span data-stu-id="af226-112">This is the C# code:</span></span>  
  
```  
using System;  
  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
      public static int testParams()  
      {  
         Stream strm;  
         SqlXmlParameter p;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);        
         cmd.CommandText = "SELECT FirstName, LastName FROM Person.Contact WHERE LastName=? For XML Auto";  
         p = cmd.CreateParameter();  
         p.Value = "Achong";  
         string strResult;  
         try   
         {  
            strm = cmd.ExecuteStream();  
            strm.Position = 0;  
            using(StreamReader sr = new StreamReader(strm))  
            {  
               Console.WriteLine(sr.ReadToEnd());  
            }  
         }  
         catch (SqlXmlException e)  
         {  
            //in case of an error, this prints error returned.  
            e.ErrorStream.Position=0;  
            strResult=new StreamReader(e.ErrorStream).ReadToEnd();  
            System.Console.WriteLine(strResult);  
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
  
### <a name="to-test-the-application"></a><span data-ttu-id="af226-113">Pour tester l'application</span><span class="sxs-lookup"><span data-stu-id="af226-113">To test the application</span></span>  
  
1.  <span data-ttu-id="af226-114">Enregistrez dans un dossier le code C# (DocSample.cs) fourni dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="af226-114">Save the C# code (DocSample.cs) provided in this topic in a folder.</span></span>  
  
2.  <span data-ttu-id="af226-115">Compilez le code.</span><span class="sxs-lookup"><span data-stu-id="af226-115">Compile the code.</span></span> <span data-ttu-id="af226-116">Pour compiler le code à l'invite de commandes, utilisez :</span><span class="sxs-lookup"><span data-stu-id="af226-116">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="af226-117">Un fichier exécutable (DocSample.exe) est alors créé.</span><span class="sxs-lookup"><span data-stu-id="af226-117">This creates an executable (DocSample.exe).</span></span>  
  
3.  <span data-ttu-id="af226-118">À l'invite de commandes, exécutez DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="af226-118">At the command prompt, execute DocSample.exe.</span></span>  
  
 <span data-ttu-id="af226-119">Pour tester cet exemple, le [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework doit être installé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="af226-119">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
 <span data-ttu-id="af226-120">Au lieu de spécifier des requêtes SQL en tant que texte de commande, vous pouvez spécifier un modèle (comme illustré dans le fragment de code ci-après) qui exécute un code de mise à jour (ou « updategram », lequel est également un modèle) afin d'insérer un enregistrement de client.</span><span class="sxs-lookup"><span data-stu-id="af226-120">Instead of specifying SQL queries as the command text, you can specify a template (as shown in the following code fragment) that executes an updategram (which is also a template) to insert a customer record.</span></span> <span data-ttu-id="af226-121">Vous pouvez spécifier des modèles et des codes de mise à jour dans les fichiers et exécuter des fichiers.</span><span class="sxs-lookup"><span data-stu-id="af226-121">You can specify templates and updategrams in files and execute files.</span></span> <span data-ttu-id="af226-122">Pour plus d’informations, consultez [exécution de fichiers modèles à l’aide de la propriété CommandText](executing-template-files-by-using-the-commandtext-property.md).</span><span class="sxs-lookup"><span data-stu-id="af226-122">For more information, see [Executing Template Files by Using the CommandText Property](executing-template-files-by-using-the-commandtext-property.md).</span></span>  
  
```  
SqlXmlCommand cmd = new SqlXmlCommand("Provider=SQLOLEDB;Data Source=SqlServerName;Initial Catalog=Database; Integrated Security=SSPI;");  
Stream stm;  
cmd.CommandType = SqlXmlCommandType.UpdateGram;  
cmd.CommandText = "<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql' xmlns:updg='urn:schemas-microsoft-com:xml-updategram'>" +  
      "<updg:sync>" +  
       "<updg:before/>" +  
       "<updg:after>" +  
         "<Customer CustomerID='aaaaa' CustomerName='Some Name' CustomerTitle='SomeTitle' />" +  
       "</updg:after>" +  
       "</updg:sync>" +  
       "</ROOT>";  
  
stm = cmd.ExecuteStream();  
stm = null;  
cmd = null;  
```  
  
## <a name="using-executetostream"></a><span data-ttu-id="af226-123">Utilisation de la méthode ExecuteToStream</span><span class="sxs-lookup"><span data-stu-id="af226-123">Using ExecuteToStream</span></span>  
 <span data-ttu-id="af226-124">Si vous disposez d’un flux existant, vous pouvez utiliser la méthode ExecuteToStream au lieu de créer un objet de flux et d’utiliser la méthode Execute.</span><span class="sxs-lookup"><span data-stu-id="af226-124">If you have an existing stream, you can use the ExecuteToStream method instead of creating a Stream object and using the Execute method.</span></span> <span data-ttu-id="af226-125">Le code de l’exemple précédent est révisé ici pour utiliser la méthode ExecuteToStream :</span><span class="sxs-lookup"><span data-stu-id="af226-125">The code from the preceding example is revised here to use the ExecuteToStream method:</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
   static string ConnString = "Provider=SQLOLEDB;Server=SqlServerName;database=AdventureWorks;Integrated Security=SSPI;";  
   public static int testParams()  
   {  
      SqlXmlParameter p;  
      MemoryStream ms = new MemoryStream();  
      StreamReader sr = new StreamReader(ms);  
      ms.Position = 0;  
      SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
      cmd.CommandText = "select FirstName, LastName from Person.Contact where LastName = ? For XML Auto";  
      p = cmd.CreateParameter();  
      p.Value = "Achong";  
      cmd.ExecuteToStream(ms);  
      ms.Position = 0;  
      Console.WriteLine(sr.ReadToEnd());  
      return 0;        
   }  
   public static int Main(String[] args)  
   {  
      testParams();     
      return 0;  
   }  
}  
```  
  
> [!NOTE]  
>  <span data-ttu-id="af226-126">Vous pouvez également utiliser le ExecuteXMLReadermethod qui retourne un objet XmlReader.</span><span class="sxs-lookup"><span data-stu-id="af226-126">You can also use the ExecuteXMLReadermethod that returns an XmlReader object.</span></span> <span data-ttu-id="af226-127">Pour plus d’informations, consultez [exécution de requêtes SQL à l’aide de la méthode ExecuteXmlReader](executing-sql-queries-by-using-the-executexmlreader-method.md).</span><span class="sxs-lookup"><span data-stu-id="af226-127">For more information, see [Executing SQL Queries by Using the ExecuteXMLReader Method](executing-sql-queries-by-using-the-executexmlreader-method.md).</span></span>  
  
  
