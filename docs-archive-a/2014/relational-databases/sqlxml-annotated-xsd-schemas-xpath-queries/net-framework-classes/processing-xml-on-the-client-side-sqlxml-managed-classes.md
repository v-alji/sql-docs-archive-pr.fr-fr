---
title: Traitement du code XML côté client (classes managées SQLXML) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- processing XML on client side [SQLXML]
- client-side XML formatting
- Managed Classes [SQLXML], client-side XML formatting
- SQLXML Managed Classes, client-side XML formatting
- ClientSideXml property
ms.assetid: 5e7ecf18-66fc-49ff-bc50-83635cd7ac0b
author: rothja
ms.author: jroth
ms.openlocfilehash: fb90f7c5c823c750b64f47d0c9df9551b9f857b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600751"
---
# <a name="processing-xml-on-the-client-side-sqlxml-managed-classes"></a><span data-ttu-id="f385c-102">traitement du XML côté client (classes managées SQLXML)</span><span class="sxs-lookup"><span data-stu-id="f385c-102">Processing XML on the Client Side (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="f385c-103">Cet exemple illustre l’utilisation de la propriété ClientSideXml.</span><span class="sxs-lookup"><span data-stu-id="f385c-103">This example illustrates the use of the ClientSideXml property.</span></span> <span data-ttu-id="f385c-104">L'application exécute une procédure stockée sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="f385c-104">The application executes a stored procedure on the server.</span></span> <span data-ttu-id="f385c-105">Le résultat de la procédure stockée (un ensemble de lignes à deux colonnes) est traité sur le côté client pour produire un document XML.</span><span class="sxs-lookup"><span data-stu-id="f385c-105">The result of the stored procedure (a two-column rowset) is processed on the client side to produce an XML document.</span></span>  
  
 <span data-ttu-id="f385c-106">La procédure stockée GetContacts suivante retourne **FirstName** et **LastName** des employés dans la table Person. contact de la base de données AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="f385c-106">The following GetContacts stored procedure returns **FirstName** and **LastName** of employees in the Person.Contact table in the AdventureWorks database.</span></span>  
  
```  
USE AdventureWorks  
CREATE PROCEDURE GetContacts @LastName varchar(20)  
AS  
SELECT FirstName, LastName  
FROM   Person.Contact  
WHERE LastName = @LastName  
Go  
```  
  
 <span data-ttu-id="f385c-107">Cette application C# exécute la procédure stockée et spécifie l’option FOR XML AUTO dans la spécification de la valeur CommandText.</span><span class="sxs-lookup"><span data-stu-id="f385c-107">This C# application executes the stored procedure and specifies the FOR XML AUTO option in specifying the CommandText value.</span></span> <span data-ttu-id="f385c-108">Dans l’application, la propriété ClientSideXml de l’objet SqlXmlCommand a la valeur true.</span><span class="sxs-lookup"><span data-stu-id="f385c-108">In the application, the ClientSideXml property of the SqlXmlCommand object is set to true.</span></span> <span data-ttu-id="f385c-109">Cela vous permet d'exécuter les procédures stockées préexistantes qui retournent un ensemble de lignes et lui appliquent une transformation XML.</span><span class="sxs-lookup"><span data-stu-id="f385c-109">This allows you to execute preexisting stored procedures that return a rowset and apply an XML transformation to it on the client.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f385c-110">Dans le code, vous devez fournir le nom de l'instance de Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="f385c-110">In the code, you must provide the name of the instance of Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in the connection string.</span></span>  
  
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
         SqlXmlParameter p;  
         SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
         cmd.ClientSideXml = true;  
         cmd.CommandText = "EXEC GetContacts ? FOR XML NESTED";  
         p = cmd.CreateParameter();  
         p.Value = "Achong";  
         using (Stream strm = cmd.ExecuteStream())   
         {  
            using (StreamReader sr = new StreamReader(strm))  
                  {  
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
  
 <span data-ttu-id="f385c-111">Pour tester cet exemple, le [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework doit être installé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="f385c-111">To test this example, you must have the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework installed on your computer.</span></span>  
  
### <a name="to-test-the-application"></a><span data-ttu-id="f385c-112">Pour tester l'application</span><span class="sxs-lookup"><span data-stu-id="f385c-112">To test the application</span></span>  
  
1.  <span data-ttu-id="f385c-113">Créez la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="f385c-113">Create the stored procedure.</span></span>  
  
2.  <span data-ttu-id="f385c-114">Enregistrez le code C# (DocSample.cs) fourni dans cet exemple dans un dossier.</span><span class="sxs-lookup"><span data-stu-id="f385c-114">Save the C# code (DocSample.cs) that is provided in this example in a folder.</span></span> <span data-ttu-id="f385c-115">Modifiez le code pour spécifier les informations de connexion et de mot de passe appropriées.</span><span class="sxs-lookup"><span data-stu-id="f385c-115">Edit the code to specify appropriate login and password information.</span></span>  
  
3.  <span data-ttu-id="f385c-116">Compilez le code.</span><span class="sxs-lookup"><span data-stu-id="f385c-116">Compile the code.</span></span> <span data-ttu-id="f385c-117">Pour compiler le code à l'invite de commandes, utilisez :</span><span class="sxs-lookup"><span data-stu-id="f385c-117">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DocSample.cs  
    ```  
  
     <span data-ttu-id="f385c-118">Un fichier exécutable (DocSample.exe) est alors créé.</span><span class="sxs-lookup"><span data-stu-id="f385c-118">This creates an executable (DocSample.exe).</span></span>  
  
4.  <span data-ttu-id="f385c-119">À l'invite de commandes, exécutez DocSample.exe.</span><span class="sxs-lookup"><span data-stu-id="f385c-119">At the command prompt, execute DocSample.exe.</span></span>  
  
  
