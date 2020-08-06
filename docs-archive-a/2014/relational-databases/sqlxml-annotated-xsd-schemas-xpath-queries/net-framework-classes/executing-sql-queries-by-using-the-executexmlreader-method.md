---
title: Exécution de requêtes SQL à l’aide de la méthode ExecuteXMLReader | Microsoft Docs
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
- ExecuteXmlReader method
- SQL queries [SQLXML]
ms.assetid: f106a4c5-8d6e-40c0-bf1f-11e121afcb01
author: rothja
ms.author: jroth
ms.openlocfilehash: 1570e877ae84a813e5a053df34c35d5fe840969c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610528"
---
# <a name="executing-sql-queries-by-using-the-executexmlreader-method"></a><span data-ttu-id="e011e-102">Exécution de requêtes SQL à l'aide de la méthode ExecuteXMLReader</span><span class="sxs-lookup"><span data-stu-id="e011e-102">Executing SQL Queries by Using the ExecuteXMLReader Method</span></span>
  <span data-ttu-id="e011e-103">Au lieu d’utiliser la méthode ExecuteToStream, vous pouvez utiliser la méthode ExecuteXmlReader de l’objet SqlXmlCommand pour exécuter des commandes.</span><span class="sxs-lookup"><span data-stu-id="e011e-103">Instead of using the ExecuteToStream method, you can use the ExecuteXmlReader method of the SqlXmlCommand object to execute commands.</span></span> <span data-ttu-id="e011e-104">Cette méthode retourne un objet XmlReader qui peut être utilisé pour le traitement supplémentaire du résultat (qui, dans cet exemple, imprime les noms d’éléments ou d’attributs et les valeurs).</span><span class="sxs-lookup"><span data-stu-id="e011e-104">This method returns an XmlReader object that can be used for further processing of the result (which in this example is printing the element or attribute names and the values).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e011e-105">Dans le code, vous devez fournir le nom de l'instance de Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="e011e-105">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
```  
using System;  
using Microsoft.Data.SqlXml;  
using System.IO;  
using System.Xml;  
   class Test  
   {  
      static string ConnString = "Provider=SQLOLEDB;Server=(local);database=AdventureWorks2012;Integrated Security=SSPI";  
      public static int testParams()  
      {  
         SqlXmlParameter p;  
         XmlReader Reader;  
         XmlTextWriter tw;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.CommandText = "select FirstName, LastName from Person.Person where LastName = ? For XML Auto";  
         p = cmd.CreateParameter();  
         p.Value = "Achong";  
         Reader = cmd.ExecuteXmlReader();  
            tw = new XmlTextWriter(Console.Out);  
         Reader.MoveToContent();  
         tw.WriteNode(Reader, false);  
         tw.Flush();  
         tw.Close();  
         Reader.Close();  
  
         return 0;  
      }  
  
      static int Main(string[] args)  
      {  
         testParams();  
         return 0;  
      }  
   }  
```  
  
### <a name="to-test-the-application"></a><span data-ttu-id="e011e-106">Pour tester l'application</span><span class="sxs-lookup"><span data-stu-id="e011e-106">To test the application</span></span>  
  
1.  <span data-ttu-id="e011e-107">Assurez-vous que le [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework est installé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="e011e-107">Make sure that you have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
2.  <span data-ttu-id="e011e-108">Enregistrez le code C# (DocSample.cs) fourni dans cette rubrique dans un dossier.</span><span class="sxs-lookup"><span data-stu-id="e011e-108">Save the C# code (DocSample.cs) that is provided in this topic in a folder.</span></span>  
  
3.  <span data-ttu-id="e011e-109">Compilez le code.</span><span class="sxs-lookup"><span data-stu-id="e011e-109">Compile the code.</span></span> <span data-ttu-id="e011e-110">Pour compiler le code à l'invite de commandes, utilisez :</span><span class="sxs-lookup"><span data-stu-id="e011e-110">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="e011e-111">Un fichier exécutable (DocSample.exe) est alors créé.</span><span class="sxs-lookup"><span data-stu-id="e011e-111">This creates an executable (DocSample.exe).</span></span>  
  
4.  <span data-ttu-id="e011e-112">À l'invite de commandes, exécutez DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="e011e-112">At the command prompt, execute DocSample.exe.</span></span>  
  
  
