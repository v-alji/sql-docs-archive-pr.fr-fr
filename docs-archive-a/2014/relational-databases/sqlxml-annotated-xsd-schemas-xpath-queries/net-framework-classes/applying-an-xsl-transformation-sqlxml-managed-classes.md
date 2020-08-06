---
title: Application d’une transformation XSL (classes managées SQLXML) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- applying XSL transformations [SQLXML]
- Managed Classes [SQLXML], applying XSL transformations
- SQLXML Managed Classes, applying XSL transformations
- XSL Transformations [SQLXML]
ms.assetid: 8562043b-3e9f-41a3-bb41-92b9f14363c4
author: rothja
ms.author: jroth
ms.openlocfilehash: d3225d838db284e2a34ebd41edb109400d0b72f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610531"
---
# <a name="applying-an-xsl-transformation-sqlxml-managed-classes"></a><span data-ttu-id="cf409-102">Application d'une transformation XSL (classes managées SQLXML)</span><span class="sxs-lookup"><span data-stu-id="cf409-102">Applying an XSL Transformation (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="cf409-103">Dans cet exemple, une requête SQL est exécutée sur la base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="cf409-103">In this example, an SQL query is executed against the AdventureWorks database.</span></span> <span data-ttu-id="cf409-104">La transformation XSL est appliquée au résultat de la requête pour générer une table à deux colonnes comportant respectivement le prénom et le nom des employés.</span><span class="sxs-lookup"><span data-stu-id="cf409-104">The XSL transformation is applied to the query result to generate a two-column table of the employees' first and last names.</span></span>  
  
 <span data-ttu-id="cf409-105">La propriété XslPath de l’objet SqlXmlCommand est utilisée pour spécifier le fichier XSL et son chemin d’accès au répertoire.</span><span class="sxs-lookup"><span data-stu-id="cf409-105">The XslPath property of the SqlXmlCommand object is used to specify the XSL file and its directory path.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cf409-106">Dans le code, vous devez fournir le nom de l'instance de Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="cf409-106">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
      public static int testXSL()  
      {  
         //Stream strm;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandText = "SELECT TOP 20 FirstName, LastName FROM Person.Contact FOR XML AUTO";  
         cmd.XslPath = "MyXSL.xsl";  
         cmd.RootTag = "root";  
         using (Stream strm = cmd.ExecuteStream()){  
            using (StreamReader sr = new StreamReader(strm)){  
               Console.WriteLine(sr.ReadToEnd());  
            }  
        }  
         return 0;  
      }  
      public static int Main(String[] args)  
      {  
         testXSL();     
         return 0;  
      }  
   }  
```  
  
 <span data-ttu-id="cf409-107">Voici la feuille de style XSL que vous pouvez utiliser pour tester l'application :</span><span class="sxs-lookup"><span data-stu-id="cf409-107">This is the XSL style sheet you can use to test the application:</span></span>  
  
```  
<?xml version='1.0' encoding='UTF-8'?>  
 <xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">   
    <xsl:output method="html"/>  
    <xsl:template match = '*'>  
        <xsl:apply-templates />  
    </xsl:template>  
    <xsl:template match = 'Person.Contact'>  
       <TR>  
         <TD><xsl:value-of select = '@FirstName' /></TD>  
         <TD><B><xsl:value-of select = '@LastName' /></B></TD>  
       </TR>  
    </xsl:template>  
    <xsl:template match = '/'>  
      <HTML>  
        <HEAD>  
           <STYLE>th { background-color: #CCCCCC }</STYLE>  
        </HEAD>  
        <BODY>  
         <TABLE border='1' style='width:300;'>  
           <TR><TH colspan='2'>Contacts</TH></TR>  
           <TR><TH >First name</TH><TH>Last name</TH></TR>  
           <xsl:apply-templates select = 'root' />  
         </TABLE>  
        </BODY>  
      </HTML>  
    </xsl:template>  
</xsl:stylesheet>  
```  
  
 <span data-ttu-id="cf409-108">Pour tester cet exemple, le [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework doit être installé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="cf409-108">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="cf409-109">Pour tester l'application</span><span class="sxs-lookup"><span data-stu-id="cf409-109">To test the application</span></span>  
  
1.  <span data-ttu-id="cf409-110">Enregistrez la feuille de style XSL dans un fichier (MyXSL.xsl).</span><span class="sxs-lookup"><span data-stu-id="cf409-110">Save the XSL style sheet in a file (MyXSL.xsl).</span></span>  
  
2.  <span data-ttu-id="cf409-111">Enregistrez le code C# (DocSample.cs) fourni dans cet exemple dans le même dossier que celui de la feuille de style.</span><span class="sxs-lookup"><span data-stu-id="cf409-111">Save the C# code (DocSample.cs) that is provided in this example in the same folder in which the style sheet is stored.</span></span>  
  
3.  <span data-ttu-id="cf409-112">Compilez le code.</span><span class="sxs-lookup"><span data-stu-id="cf409-112">Compile the code.</span></span> <span data-ttu-id="cf409-113">Pour compiler le code à l'invite de commandes, utilisez :</span><span class="sxs-lookup"><span data-stu-id="cf409-113">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="cf409-114">Un fichier exécutable (DocSample.exe) est alors créé.</span><span class="sxs-lookup"><span data-stu-id="cf409-114">This creates an executable (DocSample.exe).</span></span>  
  
4.  <span data-ttu-id="cf409-115">À l'invite de commandes, exécutez DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="cf409-115">At the command prompt, execute DocSample.exe.</span></span>  
  
## <a name="applying-an-xsl-transformation-in-the-net-framework"></a><span data-ttu-id="cf409-116">Application d'une Transformation XSL dans le .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cf409-116">Applying an XSL Transformation in the .NET Framework</span></span>  
 <span data-ttu-id="cf409-117">Au lieu d'appliquer une transformation XSL dans la couche intermédiaire, comme décrit précédemment, vous pouvez appliquer une transformation XSL côté client (dans le .NET Framework).</span><span class="sxs-lookup"><span data-stu-id="cf409-117">Instead of applying an XSL transformation in the middle tier, as described previously, you can apply an XSL transformation on the client side (in the .NET Framework).</span></span> <span data-ttu-id="cf409-118">Le code C# modifié suivant montre comment la transformation XSL est appliquée dans le .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cf409-118">The following revised C# code shows how the XSL transformation is applied in the .NET Framework.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cf409-119">Dans le code, vous devez fournir le nom de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="cf409-119">In the code, you must provide the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using System.Xml;  
using Microsoft.Data.SqlXml;  
using System.IO;  
using System.Xml.XPath;  
using System.Xml.Xsl;  
  
class Test  
{  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks;Integrated Security=SSPI";  
      public static int testXSL()  
      {  
         //Stream strm;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandText = "SELECT TOP 20 FirstName, LastName FROM Person.Contact FOR XML AUTO";  
         cmd.RootTag = "root";  
         using (Stream strm = cmd.ExecuteStream()){  
            XmlReader reader = new XmlReader(strm);  
            XPathDocument xd = new XPathDocument(reader, XmlSpace.Preserve);  
            XslCompiledTransform xslt = new XslCompiledTransform();  
            xslt.Load("MyXSL.xsl");  
            XmlWriter writer = XmlWriter.Create("xslt_output.html");  
            xslt.Transform(xd, writer);  
            reader.Close();  
            writer.Close();  
         }  
         return 0;  
      }  
      public static int Main(String[] args)  
      {  
         testXSL();     
         return 0;  
      }  
   }  
```  
  
  
